---
title: Microsoft 365 のハイブリッド ID とディレクトリ同期
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Microsoft 365、Active Directory ドメイン サービスのクリーンアップ、および Azure Active Directory Connect ツールとのディレクトリ同期について説明します。
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927546"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="a932d-103">Microsoft 365 のハイブリッド ID とディレクトリ同期</span><span class="sxs-lookup"><span data-stu-id="a932d-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="a932d-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a932d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a932d-105">ビジネス ニーズと技術的要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、Microsoft 365 を採用している企業のお客様にとって最も一般的な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="a932d-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="a932d-106">ディレクトリ同期を使用すると、Active Directory ドメイン サービス (AD DS) の ID を管理し、ユーザー アカウント、グループ、および連絡先に対する更新はすべて、Microsoft 365 サブスクリプションの Azure Active Directory (Azure AD) テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="a932d-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="a932d-107">DS ADが初めて同期される場合、Microsoft 365 ライセンスが自動的に割り当てられるのではなく、電子メールなどの Microsoft 365 サービスにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a932d-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="a932d-108">最初に使用場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-108">You must first assign them a usage location.</span></span> <span data-ttu-id="a932d-109">次に、グループ メンバーシップを使用して、個別または動的にこれらのユーザー アカウントにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a932d-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="a932d-110">ハイブリッド ID の認証</span><span class="sxs-lookup"><span data-stu-id="a932d-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="a932d-111">ハイブリッド ID モデルを使用する場合、認証には次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="a932d-112">管理された認証</span><span class="sxs-lookup"><span data-stu-id="a932d-112">Managed authentication</span></span>

  <span data-ttu-id="a932d-113">Azure ADは、ローカルに保存されたハッシュ バージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスのソフトウェア エージェントに資格情報を送信して、オンプレミスの AD DS によって認証されます。</span><span class="sxs-lookup"><span data-stu-id="a932d-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="a932d-114">フェデレーション認証</span><span class="sxs-lookup"><span data-stu-id="a932d-114">Federated authentication</span></span>

  <span data-ttu-id="a932d-115">Azure AD認証を要求するクライアント コンピューターを別の ID プロバイダーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="a932d-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="a932d-116">管理された認証</span><span class="sxs-lookup"><span data-stu-id="a932d-116">Managed authentication</span></span>

<span data-ttu-id="a932d-117">管理認証には、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="a932d-118">パスワード ハッシュ同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="a932d-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="a932d-119">Azure AD認証自体を実行します。</span><span class="sxs-lookup"><span data-stu-id="a932d-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="a932d-120">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="a932d-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="a932d-121">Azure AD DS AD認証を実行しています。</span><span class="sxs-lookup"><span data-stu-id="a932d-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="a932d-122">パスワード ハッシュ同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="a932d-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="a932d-123">PHS では、DS ユーザー AD Microsoft 365 と同期し、オンプレミスでユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="a932d-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="a932d-124">ユーザー パスワードのハッシュは、AD DS から Azure AD に同期され、ユーザーはオンプレミスとクラウドで同じパスワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a932d-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="a932d-125">これは、Azure ADで DS ID の認証を有効にする最も簡単なAD。</span><span class="sxs-lookup"><span data-stu-id="a932d-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![パスワード ハッシュ同期 (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="a932d-127">オンプレミスでパスワードを変更またはリセットすると、新しいパスワード ハッシュが Azure AD に同期され、ユーザーはクラウド リソースとオンプレミス リソースに対して常に同じパスワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a932d-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="a932d-128">ユーザー のパスワードは、Azure サーバーに送信AD、クリア テキストで azure AD保存されません。</span><span class="sxs-lookup"><span data-stu-id="a932d-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="a932d-129">Id Protection など、Azure ADの一部のプレミアム機能では、どの認証方法が選択されているに関係なく PHS が必要です。</span><span class="sxs-lookup"><span data-stu-id="a932d-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="a932d-130">詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a932d-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="a932d-131">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="a932d-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="a932d-132">PTA は、1 つ以上のオンプレミス サーバーで実行されているソフトウェア エージェントを使用して Azure AD 認証サービスの簡単なパスワード検証を提供し、AD DS を使用してユーザーを直接検証します。</span><span class="sxs-lookup"><span data-stu-id="a932d-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="a932d-133">PTA では、DS ユーザー AD Microsoft 365 と同期し、オンプレミスでユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="a932d-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![パススルー認証 (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="a932d-135">PTA を使用すると、ユーザーはオンプレミスのアカウントとパスワードを使用して、オンプレミスと Microsoft 365 の両方のリソースとアプリケーションにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="a932d-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="a932d-136">この構成では、Azure サーバーにパスワード ハッシュを格納せずに、AD DS に対してユーザーのパスワードを直接検証AD。</span><span class="sxs-lookup"><span data-stu-id="a932d-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="a932d-137">PTA は、セキュリティ要件を持つ組織でも、オンプレミスのユーザー アカウントの状態、パスワード ポリシー、ログオン時間を直ちに適用します。</span><span class="sxs-lookup"><span data-stu-id="a932d-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="a932d-138">詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a932d-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="a932d-139">フェデレーション認証</span><span class="sxs-lookup"><span data-stu-id="a932d-139">Federated authentication</span></span>

<span data-ttu-id="a932d-140">フェデレーション認証は、主に、より複雑な認証要件を持つ大規模なエンタープライズ組織向けです。</span><span class="sxs-lookup"><span data-stu-id="a932d-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="a932d-141">AD DS ID は Microsoft 365 と同期され、ユーザー アカウントはオンプレミスで管理されます。</span><span class="sxs-lookup"><span data-stu-id="a932d-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="a932d-142">フェデレーション認証では、ユーザーはオンプレミスとクラウドで同じパスワードを持ち、Microsoft 365 を使用するために再びサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a932d-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="a932d-143">フェデレーション認証は、スマートカードベース認証やサードパーティの多要素認証などの追加の認証要件をサポートできます。通常、組織が Azure AD でネイティブにサポートされていない認証要件を持っている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="a932d-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="a932d-144">詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a932d-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="a932d-145">サード パーティ認証と ID プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a932d-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="a932d-146">オンプレミスのディレクトリ オブジェクトは Microsoft 365 に同期され、クラウド リソース アクセスは主にサード パーティ ID プロバイダー (IdP) によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="a932d-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="a932d-147">組織でサード パーティのフェデレーション ソリューションを使用している場合は、サード パーティのフェデレーション ソリューションが Azure AD と互換性がある場合は、Microsoft 365 のソリューションを使用してサインオンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a932d-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="a932d-148">詳細については [、「Azure ADフェデレーション互換性リスト](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a932d-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="a932d-149">AD DS の準備</span><span class="sxs-lookup"><span data-stu-id="a932d-149">AD DS Preparation</span></span>

<span data-ttu-id="a932d-150">同期を使用して Microsoft 365 へのシームレスな移行を実現するには、Microsoft 365 ディレクトリ同期の展開を開始する前に、AD DS フォレストを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="a932d-151">ディレクトリの準備では、次のタスクに重点を置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="a932d-152">重複する **proxyAddress 属性と** **userPrincipalName 属性を削除** します。</span><span class="sxs-lookup"><span data-stu-id="a932d-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="a932d-153">有効な **userPrincipalName 属性を使用して、空の userPrincipalName** 属性と無効な **userPrincipalName 属性を更新** します。</span><span class="sxs-lookup"><span data-stu-id="a932d-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="a932d-154">**givenName**、 surname ( **sn** ) 、 **sAMAccountName**、 **displayName**、 **mail**、 **proxyAddresses**、 **mailNickname**、 **userPrincipalName** 属性の無効で疑いがある文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="a932d-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="a932d-155">属性の準備の詳細については、「Azure Active Directory 同期ツールによって同期される属性の一覧」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=396719)。</span><span class="sxs-lookup"><span data-stu-id="a932d-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a932d-156">これらは、Azure が Connect で同期AD属性です。</span><span class="sxs-lookup"><span data-stu-id="a932d-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="a932d-157">複数フォレストの展開に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a932d-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="a932d-158">複数のフォレストと SSO オプションの場合は、Azure のカスタム インストール [を使用して](/azure/active-directory/hybrid/how-to-connect-install-custom)接続ADします。</span><span class="sxs-lookup"><span data-stu-id="a932d-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="a932d-159">組織に認証用の複数のフォレスト (ログオン フォレスト) がある場合は、次の情報を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a932d-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="a932d-160">**フォレストの統合を検討してください。**</span><span class="sxs-lookup"><span data-stu-id="a932d-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="a932d-161">一般に、複数のフォレストを維持するために必要なオーバーヘッドが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="a932d-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="a932d-162">組織に個別のフォレストの必要性を指示するセキュリティ上の制約がない限り、オンプレミス環境の簡素化を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a932d-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="a932d-163">**プライマリ ログオン フォレストでのみ使用します。**</span><span class="sxs-lookup"><span data-stu-id="a932d-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="a932d-164">Microsoft 365 の初期ロールアウトでは、プライマリ ログオン フォレストにのみ Microsoft 365 を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="a932d-165">マルチフォレスト AD DS 展開を統合できない場合、または他のディレクトリ サービスを使用して ID を管理できない場合は、Microsoft またはパートナーの助けを借りてこれらを同期できます。</span><span class="sxs-lookup"><span data-stu-id="a932d-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="a932d-166">詳細 [については、「トポロジ for Azure AD接続」](/azure/active-directory/hybrid/plan-connect-topologies) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a932d-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="a932d-167">ディレクトリ同期に依存する機能</span><span class="sxs-lookup"><span data-stu-id="a932d-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="a932d-168">ディレクトリ同期は、次の機能に必要です。</span><span class="sxs-lookup"><span data-stu-id="a932d-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="a932d-169">Azure AD シームレス シングル Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="a932d-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="a932d-170">Skype の共存</span><span class="sxs-lookup"><span data-stu-id="a932d-170">Skype coexistence</span></span>
- <span data-ttu-id="a932d-171">以下を含む Exchange ハイブリッド展開。</span><span class="sxs-lookup"><span data-stu-id="a932d-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="a932d-172">オンプレミスの Exchange 環境と Microsoft 365 の間で完全に共有されたグローバル アドレス一覧 (GAL)。</span><span class="sxs-lookup"><span data-stu-id="a932d-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="a932d-173">異なるメール システムからの GAL 情報の同期。</span><span class="sxs-lookup"><span data-stu-id="a932d-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="a932d-174">Microsoft 365 サービス製品にユーザーを追加したり、Microsoft 365 サービスからユーザーを削除したりする機能。</span><span class="sxs-lookup"><span data-stu-id="a932d-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="a932d-175">これには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="a932d-175">This requires the following:</span></span>
  - <span data-ttu-id="a932d-176">ディレクトリ同期のセットアップ中に、2 つの方法で同期を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a932d-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="a932d-177">既定では、ディレクトリ同期ツールはディレクトリ情報のみをクラウドに書き込む。</span><span class="sxs-lookup"><span data-stu-id="a932d-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="a932d-178">2 者間同期を構成する場合は、限られた数のオブジェクト属性がクラウドからコピーされ、ローカルの AD DS に書き戻されるように、書き戻し機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a932d-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="a932d-179">書き戻しは Exchange ハイブリッド モードとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a932d-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="a932d-180">オンプレミスの Exchange ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="a932d-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="a932d-181">他のユーザー メールボックスをオンプレミスに維持しながら、一部のユーザー メールボックスを Microsoft 365 に移動する機能。</span><span class="sxs-lookup"><span data-stu-id="a932d-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="a932d-182">オンプレミスの差出人セーフ リストとブロックされた送信者は、Microsoft 365 にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="a932d-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="a932d-183">基本的な委任と電子メールの代理送信機能。</span><span class="sxs-lookup"><span data-stu-id="a932d-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="a932d-184">統合されたオンプレミスのスマート カードまたは多要素認証ソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="a932d-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="a932d-185">写真、サムネイル、会議室、セキュリティ グループの同期</span><span class="sxs-lookup"><span data-stu-id="a932d-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="a932d-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="a932d-186">Next step</span></span>

<span data-ttu-id="a932d-187">ハイブリッド ID を展開する準備ができたら、「ディレクトリ同期の準備 [」を参照してください](prepare-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="a932d-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
