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
description: Microsoft 365 Business Premium のセットアップ手順、サブスクライブ、ドメインおよびユーザーの追加、セキュリティポリシーの設定などについて説明します。
ms.openlocfilehash: 8ec01a58d1a15d5c4aa1cef8b81518b474630d8b
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841143"
---
# <a name="overview-of-setup"></a><span data-ttu-id="f687c-103">セットアップの概要</span><span class="sxs-lookup"><span data-stu-id="f687c-103">Overview of setup</span></span>

<span data-ttu-id="f687c-104">Microsoft 365 Business Premium セットアップに関する短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f687c-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="f687c-105">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f687c-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="f687c-106">セットアップ手順のほとんどは、ガイド付きのセットアップで行うことができますが、その他のオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f687c-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="f687c-107">手順 1: ドメインとユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="f687c-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="f687c-108">**[ドメインを追加](set-up.md#add-your-domain-to-personalize-sign-in)** します ( [サインアップ](sign-up.md)中にドメインを購入した場合、この手順は既に完了しています)。</span><span class="sxs-lookup"><span data-stu-id="f687c-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="f687c-109">**ユーザーを追加** します。</span><span class="sxs-lookup"><span data-stu-id="f687c-109">**Add users** .</span></span> <span data-ttu-id="f687c-110">次の3つの方法のいずれかでユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f687c-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="f687c-111">を [設定](set-up.md#add-users-in-the-wizard)します。</span><span class="sxs-lookup"><span data-stu-id="f687c-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="f687c-112">オンプレミスの Active directory を使用している場合は、ディレクトリ同期を使用して、 [AZURE AD Connect を使用してユーザーを追加](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) します。</span><span class="sxs-lookup"><span data-stu-id="f687c-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="f687c-113">後で管理センターで [ユーザーを追加](add-users-m365b.md) することもできます。</span><span class="sxs-lookup"><span data-stu-id="f687c-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="f687c-114">手順 2: セキュリティポリシーを設定し、デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="f687c-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="f687c-115">[ガイド付きセットアップ](set-up.md#protect-your-organization)を使用して、デバイスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f687c-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="f687c-116">また、後で [管理センター](view-policies-and-devices.md) および [Intune ポータル](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)で追加または編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="f687c-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="f687c-117">また、セットアップウィザードによって、基本的な脅威保護とデータ損失防止の設定も設定されます。</span><span class="sxs-lookup"><span data-stu-id="f687c-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="f687c-118">セットアップウィザードのセキュリティ設定に加えて、次の設定を追加することによって、セキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f687c-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="f687c-119">**メールマルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="f687c-119">**Email malware protection**</span></span>
- <span data-ttu-id="f687c-120">**ATP のフィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="f687c-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="f687c-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="f687c-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="f687c-122">**Azure Information Protection (Plan1** )</span><span class="sxs-lookup"><span data-stu-id="f687c-122">**Azure Information Protection (Plan1** )</span></span>

<span data-ttu-id="f687c-123">開始するには、「 [脅威保護を強化](increase-threat-protection.md) する」と「 [コンプライアンス機能をセットアップ](set-up-compliance.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f687c-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="f687c-124">セキュリティに関するベストプラクティスのガイドについては、「 [Microsoft 365 Business Premium をセキュリティで保護する](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f687c-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="f687c-125">手順 3: Windows 10 デバイスをセットアップおよび管理する</span><span class="sxs-lookup"><span data-stu-id="f687c-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="f687c-126">ガイド設定を完了したら、組織内のすべての Windows 10 コンピューターを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f687c-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="f687c-127">Windows 10 Pro は Microsoft 365 Business Premium の [前提条件](pre-requisites-for-data-protection.md) ですが、Windows 7 Pro、Windows 8 pro、または Windows 8.1 Pro を使用している場合は、サブスクリプションによって [windows 10 pro へのアップグレード](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)ができます。</span><span class="sxs-lookup"><span data-stu-id="f687c-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="f687c-128">「 [Windows 10 pc をセキュリティ保護](secure-win-10-pcs.md) する」の手順に従って、windows 10 デバイスのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f687c-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="f687c-129">Windows 10 デバイスを Azure AD に参加させると、Windows 10 コンピューターに設定したポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f687c-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="f687c-130">詳細については、「 [Microsoft 365 ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f687c-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="f687c-131">手順 4: Microsoft 365 Apps for business をインストールする</span><span class="sxs-lookup"><span data-stu-id="f687c-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="f687c-132">[セットアップウィザード](set-up.md#deploy-office-365-client-apps)を使用して、Windows デバイスに Office を自動的にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="f687c-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="f687c-133">ユーザーが Windows およびデバイス用の [Office アプリをインストール](https://docs.microsoft.com/office365/admin/setup/install-applications) できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f687c-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="f687c-134">詳細設定</span><span class="sxs-lookup"><span data-stu-id="f687c-134">Advanced</span></span>
- <span data-ttu-id="f687c-135">**自動操縦を使用して新しいデバイスをセットアップする**</span><span class="sxs-lookup"><span data-stu-id="f687c-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="f687c-136">[Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、ユーザーに対して **新しい** windows 10 デバイスを自動的に事前構成することができますが、これを実行できる [パートナー](https://www.microsoft.com/solution-providers/search)を取得する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f687c-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="f687c-137">[Microsoft ストア](https://go.microsoft.com/fwlink/?linkid=874598)に移動し、クラウドテクノロジエキスパートに依頼して、購入する新しいデバイスをセットアップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f687c-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="f687c-138">**オンプレミス リソースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="f687c-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="f687c-139">組織でオンプレミスの Windows Server Active Directory を使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護することができます。ただし、ローカル認証を必要とするオンプレミスのリソースへのアクセスは維持されます。</span><span class="sxs-lookup"><span data-stu-id="f687c-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="f687c-140">「 [ドメインに参加している Windows 10 デバイスを Microsoft 365 Business Premium で管理](manage-windows-devices.md) する」の手順に従って、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="f687c-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="f687c-141">この方法をお勧めします。この状態のデバイスは、ハイブリッド Azure AD 参加デバイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f687c-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="f687c-142">オンプレミスのリソース (ファイル共有やプリンターなど) を含むローカルな Active Directory が企業にある場合は、「 [Microsoft 365 Business Premium の AZURE ad 参加デバイスからオンプレミスのリソースにアクセスする」](access-resources.md)の手順に従って、azure ad に参加しているデバイスにこれらのリソースへのアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="f687c-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f687c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f687c-143">See also</span></span>

[<span data-ttu-id="f687c-144">一般法人向け Microsoft 365 のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="f687c-144">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
