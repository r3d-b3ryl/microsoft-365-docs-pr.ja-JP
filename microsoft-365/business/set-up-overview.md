---
title: セットアップの概要
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business Premium のセットアップ手順、サブスクライブからドメインとユーザーの追加、セキュリティ ポリシーの設定などについて説明します。
ms.openlocfilehash: 9d92aefb3b5666bb7c2fd2e13c9a00f074f107a7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912492"
---
# <a name="overview-of-setup"></a><span data-ttu-id="95bbd-103">セットアップの概要</span><span class="sxs-lookup"><span data-stu-id="95bbd-103">Overview of setup</span></span>

<span data-ttu-id="95bbd-104">Microsoft 365 Business Premium のセットアップに関する短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95bbd-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="95bbd-105">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95bbd-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="95bbd-106">ほとんどのセットアップ手順はガイド付きセットアップで実行できますが、他のオプションも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="95bbd-107">手順 1: ドメインとユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="95bbd-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="95bbd-108">**[ドメインを追加](set-up.md#add-your-domain-to-personalize-sign-in)** します (サインアップ中にドメインを購入した [場合、この](sign-up.md)手順は既に完了しています)。</span><span class="sxs-lookup"><span data-stu-id="95bbd-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="95bbd-109">**ユーザーを追加します**。</span><span class="sxs-lookup"><span data-stu-id="95bbd-109">**Add users**.</span></span> <span data-ttu-id="95bbd-110">次の 3 つの方法でユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="95bbd-111">ガイド付 [きセットアップで](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="95bbd-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="95bbd-112">オンプレミスの Active ディレクトリがある場合は、 [ディレクトリ同期を使用して Azure AD Connect](../enterprise/set-up-directory-synchronization.md) を使用してユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="95bbd-112">Use directory synchronization to [add users by using Azure AD Connect](../enterprise/set-up-directory-synchronization.md) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="95bbd-113">後で [管理センターでユーザー](../admin/add-users/add-users.md) を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-113">You can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="95bbd-114">手順 2: セキュリティ ポリシーを設定し、デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="95bbd-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="95bbd-115">ガイド付 [きセットアップを使用して](set-up.md#protect-your-organization) デバイス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="95bbd-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="95bbd-116">管理センターと Intune ポータルで、後で[](view-policies-and-devices.md)追加または編集[することもできます](/intune/tutorial-walkthrough-intune-portal)。</span><span class="sxs-lookup"><span data-stu-id="95bbd-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="95bbd-117">セットアップ ウィザードでは、基本的な脅威保護とデータ損失防止の設定もセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="95bbd-118">セットアップ ウィザードのセキュリティ設定に加えて、次の設定を追加することでセキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="95bbd-119">**電子メールマルウェア保護**</span><span class="sxs-lookup"><span data-stu-id="95bbd-119">**Email malware protection**</span></span>
- <span data-ttu-id="95bbd-120">**Defender for Office 365 でのフィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="95bbd-120">**Anti-phishing in Defender for Office 365**</span></span>
- <span data-ttu-id="95bbd-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="95bbd-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="95bbd-122">**Azure Information Protection (Plan1)**</span><span class="sxs-lookup"><span data-stu-id="95bbd-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="95bbd-123">開始するには、「脅威の保護 [を強化し、](increase-threat-protection.md) コンプライアンス [機能を設定する」を参照してください](set-up-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="95bbd-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="95bbd-124">ベスト セキュリティ プラクティスのロード マップについては [、「Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) をセキュリティで保護する上位 10 の方法」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="95bbd-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="95bbd-125">手順 3: Windows 10 デバイスのセットアップと管理</span><span class="sxs-lookup"><span data-stu-id="95bbd-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="95bbd-126">ガイド付きセットアップが完了したら、組織内のすべての Windows 10 コンピューターを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95bbd-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="95bbd-127">Windows 10 Pro[](pre-requisites-for-data-protection.md)は Microsoft 365 Business Premium の前提条件ですが、Windows 7 Pro、Windows 8 Pro、または Windows 8.1 Pro を使用している場合、サブスクリプションは[Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md)へのアップグレードを受ける権利があります。</span><span class="sxs-lookup"><span data-stu-id="95bbd-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).</span></span>
- <span data-ttu-id="95bbd-128">セキュリティで保護された [Windows 10 PC](secure-win-10-pcs.md) の手順に従って、Windows 10 デバイスのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="95bbd-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="95bbd-129">Windows 10 デバイスを Azure ADに参加すると、Windows 10 コンピューターに設定したポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="95bbd-130">詳細については [、「Microsoft 365 ユーザー向け Windows デバイスのセットアップ」を参照してください](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="95bbd-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="95bbd-131">手順 4: Microsoft 365 Apps for business をインストールする</span><span class="sxs-lookup"><span data-stu-id="95bbd-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="95bbd-132">セットアップ ウィザードを使用Office Windows デバイスに自動的にインストール [できます](set-up.md#deploy-office-365-client-apps)。</span><span class="sxs-lookup"><span data-stu-id="95bbd-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="95bbd-133">ユーザーが [Windows とデバイスOfficeアプリ](/office365/admin/setup/install-applications) をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-133">Let users [install Office apps](/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="95bbd-134">詳細情報</span><span class="sxs-lookup"><span data-stu-id="95bbd-134">Advanced</span></span>
- <span data-ttu-id="95bbd-135">**Autopilot を使用して新しいデバイスをセットアップする**</span><span class="sxs-lookup"><span data-stu-id="95bbd-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="95bbd-136">[Windows Autopilot](add-autopilot-devices-and-profile.md)を使用すると、ユーザー用 **に新しい** Windows 10 デバイスを自動的に事前構成できますが、[](https://www.microsoft.com/solution-providers/search)これを行えるパートナーを取得する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="95bbd-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="95bbd-137">また [、Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)にアクセスし、クラウド テクノロジの専門家に、購入した新しいデバイスのセットアップを求めすることもできます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="95bbd-138">**オンプレミス リソースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="95bbd-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="95bbd-139">組織で Windows Server Active Directory をオンプレミスで使用している場合は、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持しながら、Windows 10 デバイスを保護するために Microsoft 365 Business Premium をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="95bbd-140">「ドメインに参加している Windows 10 デバイスを [Microsoft 365 Business Premium](manage-windows-devices.md) で管理するを有効にする」の手順に従って、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="95bbd-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="95bbd-141">これは推奨される方法であり、この状態のデバイスはハイブリッド Azure と呼ばADデバイスです。</span><span class="sxs-lookup"><span data-stu-id="95bbd-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="95bbd-142">ビジネスに、いくつかのオンプレミス リソース (ファイル共有やプリンターなど) が含まれるローカル Active Directory がある場合は [、Microsoft 365 Business Premium](access-resources.md)の Azure AD に参加しているデバイスからオンプレミスリソースにアクセスする手順に従って、Azure AD に参加しているデバイスにこれらのリソースへのアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="95bbd-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="95bbd-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="95bbd-143">See also</span></span>

[<span data-ttu-id="95bbd-144">一般法人向け Microsoft 365 のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="95bbd-144">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)