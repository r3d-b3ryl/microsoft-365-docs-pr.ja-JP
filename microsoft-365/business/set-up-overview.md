---
title: セットアップの概要
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: サブスクリプションからサブスクライブ、ドメインMicrosoft 365 Business Premium追加、セキュリティ ポリシーの設定など、ユーザーの設定手順について説明します。
ms.openlocfilehash: 008a5c51698589667acc0d01649f67dab33b4c58
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245066"
---
# <a name="overview-of-setup"></a><span data-ttu-id="9c776-103">セットアップの概要</span><span class="sxs-lookup"><span data-stu-id="9c776-103">Overview of setup</span></span>

<span data-ttu-id="9c776-104">セットアップに関する短いビデオMicrosoft 365 Business Premium見る。</span><span class="sxs-lookup"><span data-stu-id="9c776-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="9c776-105">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c776-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>

<span data-ttu-id="9c776-106">ほとんどのセットアップ手順はガイド付きセットアップで実行できますが、他のオプションも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c776-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="9c776-107">手順 1: ドメインとユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="9c776-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="9c776-108">**[ドメインを追加](set-up.md#add-your-domain-to-personalize-sign-in)** します (サインアップ中にドメインを購入した [場合、この](sign-up.md)手順は既に完了しています)。</span><span class="sxs-lookup"><span data-stu-id="9c776-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="9c776-109">**ユーザーを追加します**。</span><span class="sxs-lookup"><span data-stu-id="9c776-109">**Add users**.</span></span> <span data-ttu-id="9c776-110">次の 3 つの方法でユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9c776-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="9c776-111">ガイド付 [きセットアップで](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="9c776-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="9c776-112">オンプレミスの Active ディレクトリがある場合は、[ディレクトリ同期を使用](../enterprise/set-up-directory-synchronization.md)して Azure AD Connectを使用してユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9c776-112">Use directory synchronization to [add users by using Azure AD Connect](../enterprise/set-up-directory-synchronization.md) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="9c776-113">後で [管理センターでユーザー](../admin/add-users/add-users.md) を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c776-113">You can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="9c776-114">手順 2: セキュリティ ポリシーを設定し、デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="9c776-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="9c776-115">ガイド付 [きセットアップを使用して](set-up.md#protect-your-organization) デバイス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c776-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="9c776-116">管理センターと Intune ポータルで、後で[](view-policies-and-devices.md)追加または編集[することもできます](/intune/tutorial-walkthrough-intune-portal)。</span><span class="sxs-lookup"><span data-stu-id="9c776-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="9c776-117">セットアップ ウィザードでは、基本的な脅威保護とデータ損失防止の設定もセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="9c776-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="9c776-118">セットアップ ウィザードのセキュリティ設定に加えて、次の設定を追加することでセキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="9c776-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="9c776-119">**電子メールマルウェア保護**</span><span class="sxs-lookup"><span data-stu-id="9c776-119">**Email malware protection**</span></span>
- <span data-ttu-id="9c776-120">**Defender for Office 365**</span><span class="sxs-lookup"><span data-stu-id="9c776-120">**Anti-phishing in Defender for Office 365**</span></span>
- <span data-ttu-id="9c776-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="9c776-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="9c776-122">**Azure Information Protection (Plan1)**</span><span class="sxs-lookup"><span data-stu-id="9c776-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="9c776-123">開始するには、「脅威の保護 [を強化し、](increase-threat-protection.md) コンプライアンス [機能を設定する」を参照してください](set-up-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="9c776-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="9c776-124">ベスト セキュリティ プラクティスのロード マップについては、Microsoft 365 Business Premiumセキュリティを保護するトップ[10](/office365/admin/security-and-compliance/secure-your-business-data)の方法も参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c776-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="9c776-125">手順 3: デバイスのセットアップと管理Windows 10する</span><span class="sxs-lookup"><span data-stu-id="9c776-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="9c776-126">ガイド付きセットアップが完了したら、組織内のすべてのコンピューター Windows 10保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c776-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="9c776-127">Windows 10 Pro Microsoft 365 Business Premium の前提条件[](pre-requisites-for-data-protection.md)ですが、Windows 7 Pro、Windows 8 Pro、または Windows 8.1 Pro がある場合、サブスクリプションは Windows 10 Pro へのアップグレード[を受ける権利があります](./upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="9c776-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).</span></span>
- <span data-ttu-id="9c776-128">セキュリティで保護されたデバイス[PC のWindows 10手順に](secure-win-10-pcs.md)従って、デバイスのポリシー Windows 10します。</span><span class="sxs-lookup"><span data-stu-id="9c776-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="9c776-129">デバイスを Azure Windows 10に参加AD、コンピューターに設定Windows 10ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c776-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="9c776-130">詳細については、「ユーザーのデバイス[をWindowsする」をMicrosoft 365してください](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9c776-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="9c776-131">手順 4: インストールMicrosoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="9c776-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="9c776-132">セットアップ ウィザードを使用Office、Windowsデバイスに自動的にインストール[できます](set-up.md#deploy-office-365-client-apps)。</span><span class="sxs-lookup"><span data-stu-id="9c776-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="9c776-133">ユーザーが[アプリとデバイスOfficeアプリ](/office365/admin/setup/install-applications)をWindowsできます。</span><span class="sxs-lookup"><span data-stu-id="9c776-133">Let users [install Office apps](/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="9c776-134">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9c776-134">Advanced</span></span>
- <span data-ttu-id="9c776-135">**Autopilot を使用して新しいデバイスをセットアップする**</span><span class="sxs-lookup"><span data-stu-id="9c776-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="9c776-136">Windows [Autopilot](add-autopilot-devices-and-profile.md)を使用すると、ユーザー用に新しい **Windows 10** デバイスを自動的に事前構成できますが、これを行えるパートナーを取得する [](https://www.microsoft.com/solution-providers/search)方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c776-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="9c776-137">クラウド テクノロジの専門家[に](https://go.microsoft.com/fwlink/?linkid=874598)Microsoft Store、購入した新しいデバイスをセットアップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9c776-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="9c776-138">**オンプレミス リソースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="9c776-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="9c776-139">組織で Windows Server Active Directory をオンプレミスで使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護しながら、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持できます。</span><span class="sxs-lookup"><span data-stu-id="9c776-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="9c776-140">「ドメインに参加しているデバイスをWindows 10[する](manage-windows-devices.md)」の手順に従って、Microsoft 365 Business Premiumを設定します。</span><span class="sxs-lookup"><span data-stu-id="9c776-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="9c776-141">これは推奨される方法であり、この状態のデバイスはハイブリッド Azure と呼ばADデバイスです。</span><span class="sxs-lookup"><span data-stu-id="9c776-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="9c776-142">一部のオンプレミス リソース (ファイル共有やプリンターなど) を含むローカル Active Directory がビジネスにある場合は、azure AD に参加しているデバイスにこれらのリソースへのアクセス権を与えることができます。この手順は[、「Microsoft 365 Business Premium](access-resources.md)の Azure AD に参加しているデバイスからオンプレミス リソースにアクセスする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c776-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="9c776-143">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="9c776-143">Related content</span></span>

<span data-ttu-id="9c776-144">[一般法人向け Microsoft 365 のトレーニング ビデオ](../business-video/index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="9c776-144">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>