---
title: Microsoft マネージドデスクトップテクノロジ
description: このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 914a90b4267132c9cb942740ceb974b084bcdf82
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778092"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="3f682-104">Microsoft マネージドデスクトップテクノロジ</span><span class="sxs-lookup"><span data-stu-id="3f682-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="3f682-105">このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3f682-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="3f682-106">Microsoft 365 Enterprise ライセンスは、Microsoft が管理するすべてのデスクトップユーザーに必要です。</span><span class="sxs-lookup"><span data-stu-id="3f682-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="3f682-107">サービスのライセンス要件の詳細については、「 [Microsoft マネージドデスクトップの前提条件](../get-ready/prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f682-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="3f682-108">必要なエンタープライズライセンスに含まれるすべてのコンポーネントと、サービスが Microsoft マネージドデスクトップデバイスで各コンポーネントを使用する方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3f682-108">The following are all components that are included in the required Enterprise licenses and how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3f682-109">各領域の特定の役割と責任は、「Microsoft Managed Desktop」のトピック全体で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="3f682-109">Specific roles and responsibilities for each area are detailed throughout the Microsoft Managed Desktop topic.</span></span> 

## <a name="office-365-e3"></a><span data-ttu-id="3f682-110">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="3f682-110">Office 365 E3</span></span>
 |
 --- | ---
<span data-ttu-id="3f682-111">Office 365 Standard Suite (64 ビット) \*</span><span class="sxs-lookup"><span data-stu-id="3f682-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="3f682-112">標準の Office スイートアプリケーションは、デバイス (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) に同梱されています。</span><span class="sxs-lookup"><span data-stu-id="3f682-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="3f682-113">C2R (64 ビット) をクリックして実行する () フルバージョンの Microsoft Project と Microsoft Visio は Office 365 Standard スイートに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="3f682-113">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.</span></span>  <span data-ttu-id="3f682-114">ただし、これらのアプリケーションのインストールは標準の Office スイートのインストールに依存しているため、Microsoft マネージドデスクトップでは、これらのアプリケーションを展開するために使用する既定の Intune 展開およびセキュリティグループが作成されています。ライセンスされたエンドユーザー。</span><span class="sxs-lookup"><span data-stu-id="3f682-114">However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="3f682-115">ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="3f682-115">Store Apps</span></span> |    <span data-ttu-id="3f682-116">Microsoft Sway、Power BI Desktop はデバイスと共には同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="3f682-116">Microsoft Sway, Power BI Desktop are not shipped with device.</span></span> <span data-ttu-id="3f682-117">これらのアプリは Microsoft ストアからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3f682-117">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="3f682-118">Win32 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3f682-118">Win32 Applications</span></span> |    <span data-ttu-id="3f682-119">Power BI Pro、Azure Information Protection クライアント、および Microsoft Planner はデバイスに同梱されておらず、お客様が展開用にパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f682-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="3f682-120">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3f682-120">Web Applications</span></span> |  <span data-ttu-id="3f682-121">Yammer、browser 内の Office、Delve、Flow、StaffHub、PowerApps は、デバイスに同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="3f682-121">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps are not shipped with the device.</span></span> <span data-ttu-id="3f682-122">ユーザーは、ブラウザーを使用して、これらのアプリケーションの web バージョンにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f682-122">Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="3f682-123">Skype for Business Online クラウド PBX</span><span class="sxs-lookup"><span data-stu-id="3f682-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="3f682-124">この機能は、Office 365 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3f682-124">This feature is available via Office 365.</span></span> <span data-ttu-id="3f682-125">Microsoft マネージドデスクトップでは、このサービスの一部は構成されません。</span><span class="sxs-lookup"><span data-stu-id="3f682-125">Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="3f682-126">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="3f682-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="3f682-127">Credential Guard</span><span class="sxs-lookup"><span data-stu-id="3f682-127">Credential Guard</span></span> |  <span data-ttu-id="3f682-128">Microsoft は、この機能のガイダンスを提供し、クラウドの側面を管理します。</span><span class="sxs-lookup"><span data-stu-id="3f682-128">Microsoft will provide guidance and manage cloud aspects of this feature.</span></span>
<span data-ttu-id="3f682-129">Application Virtualization (App-v)</span><span class="sxs-lookup"><span data-stu-id="3f682-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="3f682-130">Microsoft マネージドデスクトップでは、この種類の展開は Intune ではサポートされていないため、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f682-130">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="3f682-131">User Experience Virtualization (UE-V)</span><span class="sxs-lookup"><span data-stu-id="3f682-131">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="3f682-132">これは、Microsoft マネージドデスクトップで管理されているデバイスでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3f682-132">This is not used with Microsoft Managed Desktop managed devices.</span></span>
<span data-ttu-id="3f682-133">管理対象ユーザーの環境</span><span class="sxs-lookup"><span data-stu-id="3f682-133">Managed User Experience</span></span>  | <span data-ttu-id="3f682-134">これは、Microsoft マネージドデスクトップで管理されているデバイスでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3f682-134">This is not used with Microsoft Managed Desktop managed devices.</span></span> <span data-ttu-id="3f682-135">MDM は、デバイス管理のソリューションとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f682-135">MDM is used as a solution for device management.</span></span>
<span data-ttu-id="3f682-136">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3f682-136">Microsoft Defender Advanced Threat Protection</span></span> | <span data-ttu-id="3f682-137">これは、デバイスのセキュリティポリシーを管理するために Microsoft マネージドデスクトップによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f682-137">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="3f682-138">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="3f682-138">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="3f682-139">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="3f682-139">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="3f682-140">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="3f682-140">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="3f682-141">Enterprise Mobility + Security E3 および AADP のすべての側面を使用して MDM デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3f682-141">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices.</span></span>
<span data-ttu-id="3f682-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3f682-142">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="3f682-143">これは、お客様が Microsoft Managed Desktop service で使用できるオプションの機能です。</span><span class="sxs-lookup"><span data-stu-id="3f682-143">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="3f682-144">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="3f682-144">Azure Information Protection P2</span></span>  |<span data-ttu-id="3f682-145">これは、お客様が Microsoft Managed Desktop service で使用できるオプションの機能です。</span><span class="sxs-lookup"><span data-stu-id="3f682-145">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
