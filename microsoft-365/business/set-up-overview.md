---
title: セットアップの概要
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business のセットアップ手順の概要について説明します。
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074407"
---
# <a name="overview-of-setup"></a><span data-ttu-id="8e04b-103">セットアップの概要</span><span class="sxs-lookup"><span data-stu-id="8e04b-103">Overview of setup</span></span>

<span data-ttu-id="8e04b-104">セットアップ手順のほとんどはセットアップウィザードで行うことができますが、その他のオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="8e04b-105">手順 1: ドメインとユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="8e04b-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="8e04b-106">**[ドメインを追加する](set-up.md#add-your-domain-to-personalize-sign-in)**([サインアップ](sign-up.md)中にドメインを購入した場合、この手順は既に完了しています。)</span><span class="sxs-lookup"><span data-stu-id="8e04b-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="8e04b-107">**ユーザーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="8e04b-107">**Add users**.</span></span> <span data-ttu-id="8e04b-108">これは、次の3つの方法のいずれかで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="8e04b-109">[ウィザード](set-up.md#add-users-in-the-wizard)で。</span><span class="sxs-lookup"><span data-stu-id="8e04b-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="8e04b-110">オンプレミスの Active directory を使用している場合は、ディレクトリ同期を使用して、 [AZURE AD Connect を使用してユーザーを追加](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)します。</span><span class="sxs-lookup"><span data-stu-id="8e04b-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="8e04b-111">後で管理センターで[ユーザーを追加](add-users-m365b.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="8e04b-112">手順 2: セキュリティポリシーを設定し、デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="8e04b-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="8e04b-113">[セットアップウィザード](set-up.md#set-up-security-policies-and-device-configurations)を使用して、デバイスとセキュリティのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e04b-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="8e04b-114">また、後で[管理センター](view-policies-and-devices.md)および[Intune ポータル](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)で追加または編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="8e04b-115">セットアップウィザードのセキュリティ設定に加えて、次の設定を追加することによって、セキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="8e04b-116">**メールマルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="8e04b-116">**Email malware protection**</span></span>
      - <span data-ttu-id="8e04b-117">**Advanced Threat Protection (ATP) の安全なリンク**</span><span class="sxs-lookup"><span data-stu-id="8e04b-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="8e04b-118">**ATP の安全な添付ファイル機能**</span><span class="sxs-lookup"><span data-stu-id="8e04b-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="8e04b-119">**ATP のフィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="8e04b-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="8e04b-120">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="8e04b-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="8e04b-121">**データ損失防止 (DLP)**</span><span class="sxs-lookup"><span data-stu-id="8e04b-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="8e04b-122">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="8e04b-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="8e04b-123">開始するには、「 [advanced security policies をセットアップ](set-up-advanced-security.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e04b-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="8e04b-124">セキュリティに関するベストプラクティスのロードマップについては[、Microsoft 365 Business をセキュリティで保護するための10のトップの方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e04b-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="8e04b-125">手順 3: Windows 10 デバイスをセットアップおよび管理する</span><span class="sxs-lookup"><span data-stu-id="8e04b-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="8e04b-126">Windows 10 デバイスを Azure AD に参加させると、[手順 2](#step-2-set-up-security-policies-and-configure-devices)で設定したポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="8e04b-127">Windows 10 Pro は Microsoft 365 Business の[前提条件](pre-requisites-for-data-protection.md)ですが、Windows 7 Pro、Windows 8 pro、または Windows 8.1 Pro を使用している場合は、サブスクリプションによって[windows 10 pro へのアップグレード](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)ができます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="8e04b-128">[セットアップウィザード](set-up.md#set-up-security-policies-and-device-configurations)を使用して、Windows 10 デバイスのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e04b-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="8e04b-129">Stes 4: Office 365 Business をインストールする</span><span class="sxs-lookup"><span data-stu-id="8e04b-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="8e04b-130">[セットアップウィザード](set-up.md#deploy-office-365-client-apps)を使用して、Windows デバイスに Office を自動的にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="8e04b-131">管理センターから Office を自動的に[インストール](auto-install-or-uninstall-office.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e04b-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="8e04b-132">ユーザーが Windows およびデバイス用の[Office アプリをインストール](https://docs.microsoft.com/office365/admin/setup/install-applications)できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8e04b-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="8e04b-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8e04b-133">Advanced</span></span>
- <span data-ttu-id="8e04b-134">**自動操縦を使用して新しいデバイスをセットアップする**</span><span class="sxs-lookup"><span data-stu-id="8e04b-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="8e04b-135">[Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、ユーザーに対して**新しい**windows 10 デバイスを自動的に事前構成することができますが、これを実行できる[パートナー](https://www.microsoft.com/solution-providers/search)を取得する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e04b-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="8e04b-136">[Microsoft ストア](https://go.microsoft.com/fwlink/?linkid=874598)に移動して、クラウドテクノロジエキスパートに購入した新しいデバイスのセットアップを依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="8e04b-137">**オンプレミスのリソースにアクセスする**</span><span class="sxs-lookup"><span data-stu-id="8e04b-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="8e04b-138">組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="8e04b-139">「[ドメインに参加している Windows 10 デバイスが Microsoft 365 Business で管理される](manage-windows-devices.md)ようにする」の手順に従って、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8e04b-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="8e04b-140">この方法は推奨されており、この状態のデバイスはハイブリッド Azure AD 参加デバイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8e04b-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="8e04b-141">オンプレミスのリソース (ファイル共有やプリンターなど) を含むローカルな Active Directory が企業にある場合は、次の手順に従って、Azure AD に参加しているデバイスにこれらのリソースへのアクセス権を付与できます。 [Microsoft 365 Business の Azure AD に参加しているデバイス](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="8e04b-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  