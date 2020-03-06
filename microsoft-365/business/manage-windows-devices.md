---
title: Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: いくつかの手順で、Microsoft 365 を有効にして、ローカルの Active Directory に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550249"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="d2f7a-103">Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="d2f7a-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="d2f7a-104">組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="d2f7a-105">この保護をセットアップするには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="d2f7a-106">これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="d2f7a-107">このビデオでは、最も一般的なシナリオに対してこれを設定する手順について説明します。これについては、以下の手順でも詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="d2f7a-108">1. ディレクトリ同期の準備</span><span class="sxs-lookup"><span data-stu-id="d2f7a-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="d2f7a-109">ローカル Active Directory ドメインからユーザーとコンピューターを同期する前に、「 [Office 365 へのディレクトリ同期の準備](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="d2f7a-110">特に次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-110">In particular:</span></span>

   - <span data-ttu-id="d2f7a-111">次の属性について、ディレクトリに重複が存在しないことを確認してください。 **mail**、 **ProxyAddresses**、および**userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="d2f7a-112">これらの値は一意である必要があり、重複して削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="d2f7a-113">各ローカルユーザーアカウントの**userPrincipalName** (UPN) 属性を、ライセンスされた Microsoft 365 ユーザーに対応するプライマリ電子メールアドレスと一致するように構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="d2f7a-114">例: mary.shelley@contoso.com ではなく*mary@contoso* 、 \*\*</span><span class="sxs-lookup"><span data-stu-id="d2f7a-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="d2f7a-115">Active Directory ドメインが、 *.com*または *.org*などのインターネットでルーティング可能なサフィックスの代わりに、*ローカル*ユーザーアカウントの UPN サフィックスではなく、ルーティング可能*ではない*サフィックスで終わっている場合は、「[ディレクトリ同期のために非ルーティングドメインを準備する](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)」で説明されているように、まずローカルユーザーアカウントの UPN サフィックスを調整します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="d2f7a-116">2. Azure AD Connect をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="d2f7a-117">ユーザー、グループ、および連絡先をローカルの Active directory から Azure Active Directory に同期するには、Azure Active Directory Connect をインストールし、ディレクトリ同期をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="d2f7a-118">詳細については、「 [Office 365 のディレクトリ同期をセットアップ](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="d2f7a-119">この手順は、Microsoft 365 Business の場合とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="d2f7a-120">Azure AD Connect のオプションを構成する際には、**パスワード同期**、**シームレスシングルサインオン**、**パスワード書き戻し**機能を有効にすることをお勧めします。これは、Microsoft 365 Business でもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="d2f7a-121">Azure AD Connect のチェックボックスを超えてパスワードを書き戻しするには、いくつかの追加の手順があります。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="d2f7a-122">詳細については、「[方法: パスワードの書き戻しを構成](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="d2f7a-123">3. ハイブリッド Azure AD Join を構成する</span><span class="sxs-lookup"><span data-stu-id="d2f7a-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="d2f7a-124">ハイブリッド Azure AD に参加するように Windows 10 デバイスを有効にする前に、次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="d2f7a-125">Azure AD Connect の最新バージョンを実行していること。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="d2f7a-126">Azure AD connect は、ハイブリッド Azure AD に参加させるデバイスのすべてのコンピューターオブジェクトを同期しています。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="d2f7a-127">コンピューターオブジェクトが特定の組織単位 (OU) に属している場合は、それらの Ou が Azure AD connect の同期にも設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="d2f7a-128">ハイブリッド Azure AD に参加している既存のドメインに参加している Windows 10 デバイスを登録するには、[チュートリアル「管理ドメインのハイブリッド Azure Active Directory の参加を構成](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="d2f7a-129">このハイブリッドにより、既存のオンプレミスの Active Directory が Windows 10 台のコンピューターに参加し、クラウドを準備できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="d2f7a-130">4. Windows 10 の自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="d2f7a-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="d2f7a-131">Intune でモバイルデバイス管理用に Windows 10 デバイスを自動的に登録するには、「[グループポリシーを使用して windows 10 デバイスを自動的に登録](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="d2f7a-132">グループポリシーをローカルコンピューターレベルで設定することも、一括操作の場合は、グループポリシー管理コンソールおよび ADMX テンプレートを使用して、ドメインコントローラーにこのグループポリシー設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="d2f7a-133">5. シームレスなシングルサインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="d2f7a-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="d2f7a-134">シームレスな SSO は、企業のコンピューターを使用している場合に、ユーザーの Microsoft 365 クラウドリソースに自動的に署名します。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="d2f7a-135">「 [Azure Active Directory シームレスシングルサインオン: クイックスタート](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)」に記載されている2つのグループポリシーオプションのいずれかを展開するだけです。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="d2f7a-136">[**グループポリシー] オプション**では、ユーザーが設定を変更することはできませんが、**グループポリシーの優先順位**オプションで値が設定されていて、ユーザーが構成可能なままになります。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="d2f7a-137">6. Windows Hello for Business のセットアップ</span><span class="sxs-lookup"><span data-stu-id="d2f7a-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="d2f7a-138">Windows Hello for Business では、ローカルコンピューターにサインインするための強力な2要素認証 (2FA) を使用してパスワードを置き換えています。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="d2f7a-139">1つの要素は非対称キーの組で、もう1つの要素は、デバイスでサポートされている場合は、指紋または顔認識などの PIN またはその他のローカルジェスチャです。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="d2f7a-140">可能な場合は、パスワードを2FA および Windows Hello for Business に置き換えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="d2f7a-141">ハイブリッド Windows Hello for Business を構成するには、「[ハイブリッドキー信頼 Windows hello For business の前提条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="d2f7a-142">その後、「 [Configure Hybrid Windows Hello For Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d2f7a-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
