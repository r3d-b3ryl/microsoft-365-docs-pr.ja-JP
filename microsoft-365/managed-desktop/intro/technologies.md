---
title: Microsoft マネージド デスクトップのテクノロジ
description: このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1f82c339e8cbe4426c87eae045107d26201b0025
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530021"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="e27be-104">Microsoft マネージド デスクトップのテクノロジ</span><span class="sxs-lookup"><span data-stu-id="e27be-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="e27be-105">このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e27be-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="e27be-106">Microsoft 365 Enterprise ライセンスは、Microsoft が管理するすべてのデスクトップユーザーに必要です。</span><span class="sxs-lookup"><span data-stu-id="e27be-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="e27be-107">サービスのライセンス要件の詳細については、「 [Microsoft マネージドデスクトップの前提条件](../get-ready/prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e27be-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="e27be-108">このトピックでは、必要なエンタープライズライセンスに含まれるコンポーネントの概要と、サービスが Microsoft マネージドデスクトップデバイスで各コンポーネントを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e27be-108">This topic summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="e27be-109">各分野の特定の役割と責任は、Microsoft マネージドデスクトップドキュメント全体で詳細に説明されています。</span><span class="sxs-lookup"><span data-stu-id="e27be-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="e27be-110">Office 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="e27be-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="e27be-111">Microsoft 365 enterprise 用アプリ (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="e27be-111">Microsoft 365 Apps for enterprise (64-bit)</span></span> | <span data-ttu-id="e27be-112">これらの Office アプリケーションは、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote などのデバイスと共に出荷されます。</span><span class="sxs-lookup"><span data-stu-id="e27be-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="e27be-113">64ビット版の Microsoft Project と Microsoft Visio は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e27be-113">The 64-bit full versions of Microsoft Project and Microsoft Visio are not included.</span></span> <span data-ttu-id="e27be-114">ただし、これらのアプリケーションのインストールはエンタープライズインストール用の Microsoft 365 アプリに依存しているため、Microsoft Managed Desktop では既定の Microsoft Intune 展開およびセキュリティグループが作成されており、これらのアプリケーションをライセンスエンドユーザーに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="e27be-114">However, since the installation of these applications depends on the Microsoft 365 Apps for enterprise installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed end users.</span></span> <span data-ttu-id="e27be-115">詳細については、「microsoft [Project または Microsoft Visio を Microsoft マネージドデスクトップデバイスにインストール](../get-started/project-visio.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e27be-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="e27be-116">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e27be-116">OneDrive for Business</span></span> |<span data-ttu-id="e27be-117">Azure Active Directory シングルサインオンは、OneDrive for business に初めてサインインしたときにエンドユーザーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="e27be-117">Azure Active Directory Single Sign On is enabled for end users upon first sign in to OneDrive for Business.</span></span><br><br><span data-ttu-id="e27be-118">「デスクトップ」、「ドキュメント」、「画像」フォルダーの既知のフォルダーのリダイレクトが含まれています。Microsoft マネージドデスクトップで有効化および構成されている。</span><span class="sxs-lookup"><span data-stu-id="e27be-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span> 
<span data-ttu-id="e27be-119">ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="e27be-119">Store Apps</span></span> |    <span data-ttu-id="e27be-120">Microsoft Sway と Power BI は、デバイスに同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="e27be-120">Microsoft Sway and Power BI are not shipped with the device.</span></span> <span data-ttu-id="e27be-121">これらのアプリは Microsoft ストアからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e27be-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="e27be-122">Win32 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e27be-122">Win32 Applications</span></span> |    <span data-ttu-id="e27be-123">Teams はデバイスに同梱されていませんが、microsoft マネージドデスクトップデバイス用にパッケージ化され、Microsoft によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="e27be-123">Teams is not shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="e27be-124">Azure Information Protection クライアントはデバイスに同梱されていませんが、展開用にパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="e27be-124">Azure Information Protection Client is not shipped with the device, but you can have this packaged for deployment.</span></span> 
<span data-ttu-id="e27be-125">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e27be-125">Web Applications</span></span> |  <span data-ttu-id="e27be-126">Yammer、browser 内の Office、Delve、Flow、StaffHub、PowerApps、および Planner は、デバイスに同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="e27be-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner are not shipped with the device.</span></span> <span data-ttu-id="e27be-127">ユーザーは、ブラウザーを使用して、これらのアプリケーションの web バージョンにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e27be-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e3-or-e5"></a><span data-ttu-id="e27be-128">Windows 10 Enterprise E3 または E5</span><span class="sxs-lookup"><span data-stu-id="e27be-128">Windows 10 Enterprise E3 or E5</span></span>

 |
 --- | ---
<span data-ttu-id="e27be-129">Application Virtualization (App-v)</span><span class="sxs-lookup"><span data-stu-id="e27be-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="e27be-130">ユーザーは、Intune Win32 app management クライアントを使用して App-v パッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="e27be-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="e27be-131">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e27be-131">Microsoft Defender Advanced Threat Protection</span></span> |  <span data-ttu-id="e27be-132">Microsoft マネージドデスクトップは、これを使用してデバイスのセキュリティを監視します。</span><span class="sxs-lookup"><span data-stu-id="e27be-132">Microsoft Managed Desktop uses this to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="e27be-133">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="e27be-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="e27be-134">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="e27be-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="e27be-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="e27be-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="e27be-136">Enterprise Mobility + Security E3 および Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e27be-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="e27be-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e27be-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="e27be-138">このオプション機能は、Microsoft マネージドデスクトップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e27be-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="e27be-139">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="e27be-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="e27be-140">このオプション機能は、Microsoft マネージドデスクトップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e27be-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
