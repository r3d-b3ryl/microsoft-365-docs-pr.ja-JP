---
title: Microsoft 365 とオンプレミス環境との統合
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
description: この記事では、Microsoft 365 を既存のディレクトリサービスとオンプレミス環境と統合する方法について説明します。
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384861"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="eaddd-103">Microsoft 365 とオンプレミス環境との統合</span><span class="sxs-lookup"><span data-stu-id="eaddd-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="eaddd-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="eaddd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="eaddd-105">Microsoft 365 を既存のオンプレミスの Active Directory ドメインサービス (AD DS) とオンプレミスの Exchange Server、Skype for Business Server 2015、または SharePoint Server と統合することができます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="eaddd-106">AD DS を統合すると、両方の環境のユーザーアカウントを同期して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="eaddd-107">また、ユーザーがオンプレミスの資格情報を使用して両方の環境にログオンできるように、パスワードハッシュ同期 (PHS) またはシングルサインオン (SSO) を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="eaddd-108">オンプレミスのサーバー製品と統合する場合は、ハイブリッド環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="eaddd-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="eaddd-109">ハイブリッド環境は、ユーザーまたは情報を Microsoft 365 に移行する際に役立つことがあります。または、一部のユーザーまたは一部の情報を社内とクラウドに移行することができます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="eaddd-110">ハイブリッド環境の詳細については、「 [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="eaddd-111">また、Microsoft 365 管理センターでカスタマイズされたセットアップガイダンスに Azure Active Directory (Azure AD) アドバイザーを使用することもできます (Microsoft 365 にサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="eaddd-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="eaddd-112">Azure AD セットアップガイド</span><span class="sxs-lookup"><span data-stu-id="eaddd-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="eaddd-113">組織のディレクトリからユーザーを同期する</span><span class="sxs-lookup"><span data-stu-id="eaddd-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="eaddd-114">Active Directory フェデレーションサービス (AD FS) の展開アドバイザー</span><span class="sxs-lookup"><span data-stu-id="eaddd-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="eaddd-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="eaddd-115">Before you begin</span></span>

<span data-ttu-id="eaddd-116">Microsoft 365 とオンプレミス環境を統合する前に、 [ネットワークの計画とパフォーマンスの調整](network-planning-and-performance.md)も行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaddd-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="eaddd-117">利用可能な [id モデル](about-microsoft-365-identity.md)についても理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaddd-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="eaddd-118">Microsoft 365 ユーザーアカウントの管理に使用できるツールの一覧については、「 [microsoft 365 アカウントの管理](manage-microsoft-365-accounts.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="eaddd-119">Microsoft 365 を AD DS と統合する</span><span class="sxs-lookup"><span data-stu-id="eaddd-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="eaddd-120">AD DS に既存のユーザーアカウントがある場合は、これらのアカウントを Microsoft 365 で再作成して、環境間での相違点やエラーを発生させないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaddd-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="eaddd-121">ディレクトリ同期を使用すると、オンプレミスの環境とオンライン環境との間でアカウントをミラーリングできます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="eaddd-122">ディレクトリ同期を使用すると、ユーザーは環境ごとに新しい情報を記憶する必要がなくなります。また、アカウントを2回作成または更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eaddd-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="eaddd-123">ディレクトリ同期のために [、オンプレミスのディレクトリを準備](prepare-for-directory-synchronization.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaddd-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![ディレクトリ同期を使用してオンプレミスとオンラインのユーザーアカウント情報を同期された状態に保つ](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="eaddd-125">ユーザーがオンプレミスの資格情報を使用して Microsoft 365 にログオンできるようにする場合は、SSO を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="eaddd-126">SSO を使用すると、Microsoft 365 は、ユーザー認証用にオンプレミス環境を信頼するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="eaddd-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![シングルサインオンを使用すると、オンプレミスの環境とオンライン環境の両方で同じアカウントを使用できます。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="eaddd-128">パスワードのハッシュ同期またはパススルー認証 (PTA) を含む、または使用しないディレクトリ同期</span><span class="sxs-lookup"><span data-stu-id="eaddd-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="eaddd-129">ユーザーが自分のユーザーアカウント (domain\username) を使用してオンプレミス環境にログオンします。</span><span class="sxs-lookup"><span data-stu-id="eaddd-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="eaddd-130">Microsoft 365 に移行する場合は、職場または学校アカウント (user@domain.com) を使用して再度ログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaddd-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="eaddd-131">両方の環境で同じユーザー名が指定されています。</span><span class="sxs-lookup"><span data-stu-id="eaddd-131">The user name is the same in both environments.</span></span> <span data-ttu-id="eaddd-132">PHS または PTA を追加すると、ユーザーは両方の環境に対して同じパスワードを使用しますが、Microsoft 365 にログオンするときに再び資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaddd-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="eaddd-133">ディレクトリ同期 (PHS) は、最も一般的に使用されるディレクトリ同期です。</span><span class="sxs-lookup"><span data-stu-id="eaddd-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="eaddd-134">ディレクトリ同期をセットアップするには、Azure AD Connect を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaddd-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="eaddd-135">手順については、「Microsoft 365 および[AZURE AD Connect で](https://go.microsoft.com/fwlink/p/?LinkId=698537)[のディレクトリ同期をセットアップする](set-up-directory-synchronization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="eaddd-136">詳細については [、「Microsoft 365 へのディレクトリ同期の準備」を](prepare-for-directory-synchronization.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="eaddd-137">SSO を使用したディレクトリ同期</span><span class="sxs-lookup"><span data-stu-id="eaddd-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="eaddd-138">ユーザーが自分のユーザーアカウントを使用してオンプレミス環境にログオンします。</span><span class="sxs-lookup"><span data-stu-id="eaddd-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="eaddd-139">Microsoft 365 に移行すると、それらのユーザーは自動的にログオンするか、オンプレミス環境 (domain\username) に使用したものと同じ資格情報を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="eaddd-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="eaddd-140">SSO をセットアップするには、Azure AD Connect も使用します。</span><span class="sxs-lookup"><span data-stu-id="eaddd-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="eaddd-141">手順については、「 [AZURE AD Connect のカスタムインストール](https://go.microsoft.com/fwlink/p/?LinkID=698430)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="eaddd-142">詳細については、「 [シングルサインオン](https://go.microsoft.com/fwlink/p/?LinkId=698604)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="eaddd-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="eaddd-143">Azure AD Connect</span></span>

<span data-ttu-id="eaddd-144">Azure AD Connect は、DirSync、Azure AD Sync などの id 統合ツールの以前のバージョンに置き換えられました。Azure Active Directory 同期から Azure AD Connect に更新する場合は、 [アップグレード手順](https://go.microsoft.com/fwlink/p/?LinkId=733240)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaddd-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="eaddd-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaddd-145">See also</span></span>

[<span data-ttu-id="eaddd-146">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="eaddd-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
