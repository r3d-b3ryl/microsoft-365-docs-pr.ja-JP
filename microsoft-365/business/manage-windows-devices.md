---
title: Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365 を有効にして、ローカルの AD に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: d1dbfc6a35d54db653ae0f911fad05ac2ce0a993
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288037"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="52e69-103">Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="52e69-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="52e69-104">組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="52e69-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="52e69-105">これを設定するために、 **AZURE AD に参加**しているハイブリッドデバイスを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="52e69-105">To set this up, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="52e69-106">これらは、オンプレミスの Active Directory と Azure Active Directory の両方に参加しているデバイスです。</span><span class="sxs-lookup"><span data-stu-id="52e69-106">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="52e69-107">次のビデオでは、次の手順でも説明する最も一般的なシナリオに対して、この設定を行うための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="52e69-107">The following video details the steps for how to set this up for the most common scenario that is also detailed in the following steps.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="52e69-108">1. ディレクトリ同期の準備</span><span class="sxs-lookup"><span data-stu-id="52e69-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="52e69-109">ローカル Active Directory ドメインからユーザーとコンピューターを同期する前に、「 [Office 365 へのディレクトリ同期の準備](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e69-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="52e69-110">特に次のようになります。</span><span class="sxs-lookup"><span data-stu-id="52e69-110">In particular:</span></span>

   - <span data-ttu-id="52e69-111">次の属性について、ディレクトリに重複が存在しないことを確認してください。 **mail**、 **ProxyAddresses**、および**userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="52e69-111">Ensure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="52e69-112">これらの値は一意である必要があります。また、重複を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e69-112">These values should be unique and any duplicates should be removed..</span></span>
   
   - <span data-ttu-id="52e69-113">各ローカルユーザーアカウントの**userPrincipalName** (UPN) 属性は、ライセンスが付与された Microsoft 365 ユーザーに対応するプライマリ電子メールアドレスと一致するように構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52e69-113">We recommended that the **userPrincipalName** (UPN) attribute for each local user account is configured to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="52e69-114">たとえば、 *shelley @<span>contoso というよう<span>にします。* *mary @ contoso*ではなく、com</span><span class="sxs-lookup"><span data-stu-id="52e69-114">For example *mary.shelley@<span>contoso.<span>com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="52e69-115">Active Directory ドメインが、 *.com*または *.org*などのインターネットでルーティング可能なサフィックスではなく、*ローカル*のサフィックスまたは*lan*などのルーティングできないサフィックスで終わっている場合は、まず、次に示すように、最初にローカルユーザーアカウントの UPN サフィックスを調整する必要があります。[ルーティング不能なドメインをディレクトリ同期用に準備](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)します。</span><span class="sxs-lookup"><span data-stu-id="52e69-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, you will need to adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="52e69-116">2. Azure AD Connect をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="52e69-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="52e69-117">ユーザー、グループ、および連絡先をローカルの Active directory から Azure Active Directory に同期するには、Azure Active Directory Connect をインストールし、ディレクトリ同期をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="52e69-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="52e69-118">詳細については、「 [Office 365 のディレクトリ同期をセットアップ](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e69-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="52e69-119">この手順は、Microsoft 365 Business の場合とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="52e69-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="52e69-120">Azure AD Connect のオプションを構成する際には、**パスワード同期**と**シームレスなシングルサインオン**、および Microsoft 365 Business でもサポートされている**パスワード書き戻し**機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52e69-120">As you configure your options for Azure AD Connect, we recommend enabling **Password Synchronization** and **Seamless Single Sign-On**, as well as the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="52e69-121">Azure AD Connect のチェックボックスを超えてパスワードを書き戻しするには、いくつかの追加の手順があります。</span><span class="sxs-lookup"><span data-stu-id="52e69-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="52e69-122">詳細については、「[方法: パスワードの書き戻しを構成](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e69-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="52e69-123">3. ハイブリッド Azure AD Join を構成する</span><span class="sxs-lookup"><span data-stu-id="52e69-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="52e69-124">ハイブリッド Azure AD に参加するように Windows 10 デバイスを有効にする前に、次の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e69-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, you should make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="52e69-125">Azure AD connect の最新バージョンを実行していること。</span><span class="sxs-lookup"><span data-stu-id="52e69-125">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="52e69-126">Azure AD connect は、ハイブリッド Azure AD に参加させるデバイスのすべてのコンピューターオブジェクトを同期しています。</span><span class="sxs-lookup"><span data-stu-id="52e69-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="52e69-127">コンピューターオブジェクトが特定の組織単位 (OU) に属している場合は、それらの Ou が Azure AD connect の同期にも設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52e69-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="52e69-128">ハイブリッド Azure AD に参加している既存のドメインに参加している Windows 10 デバイスを登録するには、[チュートリアル「管理ドメインのハイブリッド Azure Active Directory の参加を構成](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="52e69-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="52e69-129">これにより、既存のオンプレミスの Active Directory に参加している Windows 10 台のコンピューターをハイブリッドにして、クラウドの準備を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52e69-129">This will hybrid-enable your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="52e69-130">4. Windows 10 の自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="52e69-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="52e69-131">Intune でモバイルデバイス管理用に Windows 10 デバイスを自動的に登録するには、「[グループポリシーを使用して windows 10 デバイスを自動的に登録](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e69-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="52e69-132">グループポリシーをローカルコンピューターレベルで設定したり、一括操作に使用したりすることができます。このグループポリシー設定は、グループポリシー管理コンソールと ADMX テンプレートを使用してドメインコントローラー上に作成できます。</span><span class="sxs-lookup"><span data-stu-id="52e69-132">You can set the Group Policy at a local computer level, or for bulk operations, you can create this group policy setting on your Domain Controller using the Group Policy Management Console and ADMX templates.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="52e69-133">5. シームレスなシングルサインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="52e69-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="52e69-134">ユーザーが企業のコンピューターを使用すると、シームレスな SSO によって自動的に Microsoft 365 クラウドリソースに署名されます。</span><span class="sxs-lookup"><span data-stu-id="52e69-134">Seamless SSO will automatically sign users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="52e69-135">「 [Azure Active Directory シームレスシングルサインオン: クイックスタート](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)」に記載されている2つのグループポリシーオプションのいずれかを展開するだけです。</span><span class="sxs-lookup"><span data-stu-id="52e69-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="52e69-136">[**グループポリシー** ] オプションでは、ユーザーが設定を変更することはできませんが、**グループポリシーの優先順位**オプションで値が設定されていても、ユーザーが構成可能なままになります。</span><span class="sxs-lookup"><span data-stu-id="52e69-136">The **Group Policy** option does not allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="52e69-137">6. Windows Hello for Business のセットアップ</span><span class="sxs-lookup"><span data-stu-id="52e69-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="52e69-138">Windows Hello for Business では、ローカルコンピューターにサインインするための強力な2要素認証 (2FA) を使用してパスワードを置き換えています。</span><span class="sxs-lookup"><span data-stu-id="52e69-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="52e69-139">1つの要素は非対称キーの組で、もう1つの要素は、デバイスでサポートされている場合は、指紋または顔認識などの PIN またはその他のローカルジェスチャです。</span><span class="sxs-lookup"><span data-stu-id="52e69-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="52e69-140">可能な場合は、パスワードを2FA および Windows Hello for Business に置き換えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52e69-140">We recommended that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="52e69-141">ハイブリッド Windows Hello for Business を構成するには、「[ハイブリッドキー信頼 Windows hello For business の前提条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="52e69-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="52e69-142">その後、「 [Configure Hybrid Windows Hello For Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="52e69-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
