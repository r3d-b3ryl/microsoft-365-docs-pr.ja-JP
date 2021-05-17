---
title: Microsoft 365環境との統合
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: この記事では、既存のディレクトリ サービスMicrosoft 365オンプレミス環境と統合する方法について学習します。
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923968"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="f37a3-103">Microsoft 365環境との統合</span><span class="sxs-lookup"><span data-stu-id="f37a3-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="f37a3-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="f37a3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f37a3-105">Microsoft 365 を既存のオンプレミス Active Directory ドメイン サービス (AD DS) と、Exchange Server、Skype for Business Server 2015、または SharePoint Server のオンプレミス インストールと統合できます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="f37a3-106">DS を統合AD、両方の環境のユーザー アカウントを同期および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="f37a3-107">また、パスワード ハッシュ同期 (PHS) またはシングル サインオン (SSO) を追加して、ユーザーがオンプレミスの資格情報を使用して両方の環境にログオンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="f37a3-108">オンプレミスのサーバー製品と統合する場合は、ハイブリッド環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="f37a3-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="f37a3-109">ハイブリッド環境は、ユーザーまたは情報を Microsoft 365 に移行する場合や、一部のユーザーまたは一部の情報をオンプレミスとクラウドに引き続き持つ場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="f37a3-110">ハイブリッド環境の詳細については、「ハイブリッド クラウド」 [を参照してください](../solutions/cloud-architecture-models.md#hybrid)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="f37a3-111">Microsoft 365 管理センターのカスタマイズされたセットアップ ガイダンスには、Azure Active Directory (Azure AD) アドバイザーを使用できます (Microsoft 365 にサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="f37a3-112">Azure ADセットアップ ガイド</span><span class="sxs-lookup"><span data-stu-id="f37a3-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="f37a3-113">組織のディレクトリからユーザーを同期する</span><span class="sxs-lookup"><span data-stu-id="f37a3-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="f37a3-114">Active Directory フェデレーション サービス (AD FS) 展開アドバイザー</span><span class="sxs-lookup"><span data-stu-id="f37a3-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="f37a3-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="f37a3-115">Before you begin</span></span>

<span data-ttu-id="f37a3-116">オンプレミス環境Microsoft 365統合する前に、ネットワーク計画とパフォーマンス[調整も行う必要があります](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="f37a3-117">また、使用可能な ID モデルも [理解する必要があります](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="f37a3-118">ユーザー[アカウントMicrosoft 365管理](manage-microsoft-365-accounts.md)するために使用できるツールの一覧については、「アカウントの管理」Microsoft 365参照してください。</span><span class="sxs-lookup"><span data-stu-id="f37a3-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="f37a3-119">DS とのMicrosoft 365統合ADする</span><span class="sxs-lookup"><span data-stu-id="f37a3-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="f37a3-120">AD DS に既存のユーザー アカウントがある場合は、Microsoft 365 のすべてのアカウントを再作成し、環境間の違いやエラーが発生するリスクはありません。</span><span class="sxs-lookup"><span data-stu-id="f37a3-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="f37a3-121">ディレクトリ同期は、オンプレミス環境とオンライン環境の間でこれらのアカウントをミラーリングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="f37a3-122">ディレクトリ同期を使用すると、ユーザーは環境ごとに新しい情報を記憶する必要が生じ、アカウントを 2 回作成または更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f37a3-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="f37a3-123">ディレクトリ同期のために [オンプレミス ディレクトリを準備](prepare-for-directory-synchronization.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f37a3-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![ディレクトリ同期を使用してオンプレミスとオンラインのユーザー アカウント情報を同期する](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="f37a3-125">ユーザーがオンプレミスの資格情報を使用してMicrosoft 365にログオンする場合は、SSO を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="f37a3-126">SSO を使用Microsoft 365、ユーザー認証のためにオンプレミス環境を信頼するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="f37a3-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![シングル サインオンでは、オンプレミス環境とオンライン環境の両方で同じアカウントを利用できます。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="f37a3-128">パスワード ハッシュ同期またはパススルー認証 (PTA) の使用とディレクトリの同期</span><span class="sxs-lookup"><span data-stu-id="f37a3-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="f37a3-129">ユーザーは、自分のユーザー アカウント (domain\username) を使用してオンプレミス環境にログオンします。</span><span class="sxs-lookup"><span data-stu-id="f37a3-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="f37a3-130">ユーザーがアカウントに移動Microsoft 365、仕事または学校のアカウント (user@domain.com) を使用して再度ログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f37a3-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="f37a3-131">ユーザー名は、両方の環境で同じです。</span><span class="sxs-lookup"><span data-stu-id="f37a3-131">The user name is the same in both environments.</span></span> <span data-ttu-id="f37a3-132">PHS または PTA を追加すると、ユーザーは両方の環境で同じパスワードを持ちますが、Microsoft 365 にログオンするときにそれらの資格情報を再度指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f37a3-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="f37a3-133">PHS とのディレクトリ同期は、最も一般的に使用されるディレクトリ同期です。</span><span class="sxs-lookup"><span data-stu-id="f37a3-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="f37a3-134">ディレクトリ同期を設定するには、Azure サーバーを使用AD Connect。</span><span class="sxs-lookup"><span data-stu-id="f37a3-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="f37a3-135">手順については、「高速設定を[使用](set-up-directory-synchronization.md)して、Microsoft 365 Azure AD Connect同期を設定[する」を参照してください](/azure/active-directory/hybrid/how-to-connect-install-express)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="f37a3-136">ディレクトリ同期の[準備について詳しくは、Microsoft 365。](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="f37a3-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="f37a3-137">SSO とのディレクトリ同期</span><span class="sxs-lookup"><span data-stu-id="f37a3-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="f37a3-138">ユーザーは、自分のユーザー アカウントを使用してオンプレミス環境にログオンします。</span><span class="sxs-lookup"><span data-stu-id="f37a3-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="f37a3-139">ユーザーが Microsoft 365に移動すると、自動的にログオンするか、オンプレミス環境 (domain\username) で使用するのと同じ資格情報を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="f37a3-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="f37a3-140">SSO を設定するには、Azure サーバーもAD Connect。</span><span class="sxs-lookup"><span data-stu-id="f37a3-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="f37a3-141">手順については[、「Azure AD Connect のカスタム インストール」を参照してください](/azure/active-directory/hybrid/how-to-connect-install-custom)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="f37a3-142">詳細については、「シングル サインオン [」を参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="f37a3-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="f37a3-143">Azure AD Connect</span></span>

<span data-ttu-id="f37a3-144">Azure AD Connectは、DirSync や id などの以前のバージョンの ID 統合ツールを置き換Azure AD Sync。同期から Azure への同期を更新する場合Azure Active DirectoryアップグレードAD Connect手順[を参照してください](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)。</span><span class="sxs-lookup"><span data-stu-id="f37a3-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="f37a3-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="f37a3-145">See also</span></span>

[<span data-ttu-id="f37a3-146">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="f37a3-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)