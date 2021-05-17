---
title: ユーザー Microsoft 365パスワードの管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: ユーザー アカウントのパスワードをMicrosoft 365する方法について説明します。
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905094"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="04dd8-103">ユーザー Microsoft 365パスワードの管理</span><span class="sxs-lookup"><span data-stu-id="04dd8-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="04dd8-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="04dd8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="04dd8-105">ID 構成にMicrosoft 365、ユーザー アカウント のパスワードを管理できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="04dd8-106">ユーザー アカウントは[、Microsoft 365](../admin/add-users/index.yml)管理センター、Active Directory ドメイン サービス (AD DS)、または Azure Active Directory (Azure AD) 管理センターで管理できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="04dd8-107">ユーザー アカウントのパスワードを管理する場所と方法を計画する</span><span class="sxs-lookup"><span data-stu-id="04dd8-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="04dd8-108">ユーザー アカウントを管理する場所と方法は、ユーザー アカウントに使用する id モデルによってMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="04dd8-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="04dd8-109">2 つのモデルは、クラウド専用とハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="04dd8-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="04dd8-110">クラウド専用</span><span class="sxs-lookup"><span data-stu-id="04dd8-110">Cloud-only</span></span>

<span data-ttu-id="04dd8-111">ユーザー アカウントのパスワードは、次の場所で管理します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="04dd8-112">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="04dd8-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="04dd8-113">Azure AD管理センター</span><span class="sxs-lookup"><span data-stu-id="04dd8-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="04dd8-114">ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="04dd8-114">Hybrid</span></span>

<span data-ttu-id="04dd8-115">ハイブリッド ID を使用すると、AD DS に保存されます。そのため、ユーザー アカウントのパスワードを管理するには、オンプレミスの DS ADを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04dd8-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="04dd8-116">Azure AD が既にハッシュ化されたバージョンのハッシュバージョンを AD DS に格納するパスワード ハッシュ同期 (PHS) を使用する場合でも、ユーザーとユーザーは AD DS でパスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04dd8-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="04dd8-117">パスワード [の書き戻し](#pw_writeback)を使用すると、ユーザーは Azure ADを使用して DS パスワードを変更AD。</span><span class="sxs-lookup"><span data-stu-id="04dd8-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="04dd8-118">脆弱なパスワードを防止する</span><span class="sxs-lookup"><span data-stu-id="04dd8-118">Prevent bad passwords</span></span>

<span data-ttu-id="04dd8-119">すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance)を使用してユーザー アカウントのパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04dd8-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="04dd8-120">ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="04dd8-121">たとえば、次のような組織固有の用語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="04dd8-122">ブランド名</span><span class="sxs-lookup"><span data-stu-id="04dd8-122">Brand names</span></span>
- <span data-ttu-id="04dd8-123">製品名</span><span class="sxs-lookup"><span data-stu-id="04dd8-123">Product names</span></span>
- <span data-ttu-id="04dd8-124">場所 (たとえば、会社の本部など)</span><span class="sxs-lookup"><span data-stu-id="04dd8-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="04dd8-125">会社固有の内部用語</span><span class="sxs-lookup"><span data-stu-id="04dd8-125">Company-specific internal terms</span></span>
- <span data-ttu-id="04dd8-126">会社固有の意味を持つ略語</span><span class="sxs-lookup"><span data-stu-id="04dd8-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="04dd8-127">クラウドとオンプレミスの DS[](/azure/active-directory/authentication/concept-password-ban-bad)で、悪いパスワードを[ADできます](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="04dd8-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="04dd8-128">ユーザー サインインを簡素化する</span><span class="sxs-lookup"><span data-stu-id="04dd8-128">Simplify user sign-in</span></span>

<span data-ttu-id="04dd8-129">Azure AD シームレス シングル Sign-On (Azure AD シームレス SSO) は PHS および Pass-Through 認証 (PTA) と連携して、ユーザーがパスワードを入力せずに Azure AD ユーザー アカウントを使用するサービスにサインインできます。多くの場合、ユーザー名を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04dd8-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="04dd8-130">これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="04dd8-131">Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="04dd8-132">「[Azure Active Directory シームレス シングル サインオン: クイック スタート](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04dd8-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="04dd8-133">DS に対するパスワード更新AD簡略化する</span><span class="sxs-lookup"><span data-stu-id="04dd8-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="04dd8-134">パスワードの書き戻しを使用すると、ユーザーが Azure AD 経由でパスワードをリセットし、そのパスワードを DS にADできます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="04dd8-135">ユーザーは、パスワードを更新するためにオンプレミスの DS にADする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="04dd8-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="04dd8-136">これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="04dd8-137">パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="04dd8-138">その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](/azure/active-directory/active-directory-passwords-writeback)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04dd8-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="04dd8-p108">最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04dd8-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="04dd8-141">パスワード再設定を簡素化する</span><span class="sxs-lookup"><span data-stu-id="04dd8-141">Simplify password resets</span></span>

<span data-ttu-id="04dd8-142">セルフサービス パスワードリセット (SSPR) を使用すると、ユーザーはパスワードまたはアカウントをリセットまたはロック解除できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="04dd8-143">誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="04dd8-144">パスワードのリセットを [展開する前に](#pw_writeback) 、パスワードの書き戻しを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04dd8-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="04dd8-145">「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04dd8-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>