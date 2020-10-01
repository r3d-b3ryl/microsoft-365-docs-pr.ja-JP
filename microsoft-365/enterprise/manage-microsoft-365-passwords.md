---
title: Microsoft 365 ユーザーアカウントのパスワードを管理する
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
description: Microsoft 365 ユーザーアカウントのパスワードを管理する方法について説明します。
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328511"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="ac762-103">Microsoft 365 ユーザーアカウントのパスワードを管理する</span><span class="sxs-lookup"><span data-stu-id="ac762-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="ac762-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ac762-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ac762-105">Id の構成に応じて、Microsoft 365 のユーザーアカウントのパスワードをさまざまな方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="ac762-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="ac762-106">ユーザーアカウントは、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)、Active Directory ドメインサービス (AD DS)、または Azure Active Directory (azure AD) 管理センターで管理できます。</span><span class="sxs-lookup"><span data-stu-id="ac762-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="ac762-107">ユーザーアカウントのパスワードを管理する場所と方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="ac762-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="ac762-108">ユーザーアカウントを管理する場所と方法は、Microsoft 365 で使用する id モデルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ac762-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="ac762-109">2つのモデルは、クラウド専用でハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="ac762-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="ac762-110">クラウド専用</span><span class="sxs-lookup"><span data-stu-id="ac762-110">Cloud-only</span></span>

<span data-ttu-id="ac762-111">ユーザーアカウントのパスワードを管理するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ac762-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="ac762-112">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="ac762-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- <span data-ttu-id="ac762-113">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="ac762-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="ac762-114">ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="ac762-114">Hybrid</span></span>

<span data-ttu-id="ac762-115">ハイブリッド id では、パスワードが AD DS に格納されるため、オンプレミスの AD DS ツールを使用してユーザーアカウントのパスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac762-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="ac762-116">パスワードハッシュ同期 (PHS) を使用している場合でも、Azure AD は AD DS で既にハッシュされたバージョンのハッシュ化されたバージョンを格納し、ユーザーは AD DS で自分のパスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac762-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="ac762-117">[パスワードの書き戻し](#pw_writeback)を使用すると、ユーザーは Azure ad を使用して ad DS のパスワードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac762-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="ac762-118">脆弱なパスワードを防止する</span><span class="sxs-lookup"><span data-stu-id="ac762-118">Prevent bad passwords</span></span>

<span data-ttu-id="ac762-119">すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance)を使用してユーザー アカウントのパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac762-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="ac762-120">ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac762-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="ac762-121">たとえば、次のような組織固有の用語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac762-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="ac762-122">ブランド名</span><span class="sxs-lookup"><span data-stu-id="ac762-122">Brand names</span></span>
- <span data-ttu-id="ac762-123">製品名</span><span class="sxs-lookup"><span data-stu-id="ac762-123">Product names</span></span>
- <span data-ttu-id="ac762-124">場所 (たとえば、会社の本部など)</span><span class="sxs-lookup"><span data-stu-id="ac762-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="ac762-125">会社固有の内部用語</span><span class="sxs-lookup"><span data-stu-id="ac762-125">Company-specific internal terms</span></span>
- <span data-ttu-id="ac762-126">会社固有の意味を持つ略語</span><span class="sxs-lookup"><span data-stu-id="ac762-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="ac762-127">[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)の無効なパスワードを禁止し、[オンプレミスの AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)に対して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac762-127">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="ac762-128">ユーザー サインインを簡素化する</span><span class="sxs-lookup"><span data-stu-id="ac762-128">Simplify user sign-in</span></span>

<span data-ttu-id="ac762-129">Azure ad シームレスシングルサインオン (Azure AD シームレス SSO) は、PHS とパススルー認証 (PTA) を使用して動作し、ユーザーがパスワードを入力しなくても、Azure AD ユーザーアカウントを使用するサービスにサインインしたり、多くの場合はユーザー名を入力したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac762-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="ac762-130">これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。</span><span class="sxs-lookup"><span data-stu-id="ac762-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="ac762-131">Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="ac762-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="ac762-132">「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac762-132">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="ac762-133">AD DS へのパスワードの更新を簡素化する</span><span class="sxs-lookup"><span data-stu-id="ac762-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="ac762-134">パスワードの書き戻しを使用すると、ユーザーが Azure AD 経由でパスワードをリセットできるようになります。これは、AD DS にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="ac762-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="ac762-135">ユーザーは、オンプレミスの AD DS にアクセスしてパスワードを更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac762-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="ac762-136">これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac762-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="ac762-137">パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="ac762-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="ac762-138">その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac762-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="ac762-p108">最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac762-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="ac762-141">パスワード再設定を簡素化する</span><span class="sxs-lookup"><span data-stu-id="ac762-141">Simplify password resets</span></span>

<span data-ttu-id="ac762-142">セルフサービスによるパスワードのリセット (SSPR) により、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="ac762-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="ac762-143">誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac762-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="ac762-144">パスワードのリセットを展開するには、 [パスワードの書き戻し](#pw_writeback) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac762-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="ac762-145">「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac762-145">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

