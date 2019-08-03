---
title: Microsoft マネージドデスクトップテクノロジ
description: このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f3094b1a1272b0c200271b8d5703fe7173683a6
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171737"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="872f4-104">Microsoft マネージドデスクトップテクノロジ</span><span class="sxs-lookup"><span data-stu-id="872f4-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="872f4-105">このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="872f4-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="872f4-106">Microsoft 365 Enterprise ライセンスは、Microsoft が管理するすべてのデスクトップユーザーに必要です。</span><span class="sxs-lookup"><span data-stu-id="872f4-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="872f4-107">サービスのライセンス要件の詳細については、「 [Microsoft マネージドデスクトップの前提条件](../get-ready/prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="872f4-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="872f4-108">このトピックでは、必要なエンタープライズライセンスに含まれるコンポーネントの概要と、サービスが Microsoft マネージドデスクトップデバイスで各コンポーネントを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="872f4-108">This topic summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="872f4-109">各分野の特定の役割と責任は、Microsoft マネージドデスクトップドキュメント全体で詳細に説明されています。</span><span class="sxs-lookup"><span data-stu-id="872f4-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3"></a><span data-ttu-id="872f4-110">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="872f4-110">Office 365 E3</span></span>
 |
 --- | ---
<span data-ttu-id="872f4-111">Office 365 standard suite (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="872f4-111">Office 365 standard suite(64-bit)</span></span> | <span data-ttu-id="872f4-112">標準の Office スイートアプリケーションは、デバイス (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) に同梱されています。</span><span class="sxs-lookup"><span data-stu-id="872f4-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="872f4-113">C2R (Microsoft Project の完全バージョン) および Microsoft Visio が Office 365 に含まれていない場合は、64ビット版をクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="872f4-113">The 64-bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in Office 365.</span></span> <span data-ttu-id="872f4-114">ただし、これらのアプリケーションのインストールは標準の Office スイートのインストールに依存しているため、Microsoft マネージドデスクトップでは、これらのアプリケーションを展開するために使用できる既定の Microsoft Intune 展開およびセキュリティグループが作成されています。ライセンスされたエンドユーザー。</span><span class="sxs-lookup"><span data-stu-id="872f4-114">However, since the installation of these applications depends on the standard Office suite installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed end users.</span></span> <span data-ttu-id="872f4-115">詳細については、「microsoft [Project または Microsoft Visio を Microsoft マネージドデスクトップデバイスにインストール](../get-started/project-visio.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="872f4-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md)</span></span>  
<span data-ttu-id="872f4-116">ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="872f4-116">Store Apps</span></span> |    <span data-ttu-id="872f4-117">Microsoft Sway と Power BI は、デバイスに同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="872f4-117">Microsoft Sway and Power BI are not shipped with the device.</span></span> <span data-ttu-id="872f4-118">これらのアプリは Microsoft ストアからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="872f4-118">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="872f4-119">Win32 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="872f4-119">Win32 Applications</span></span> |    <span data-ttu-id="872f4-120">Teams はデバイスに同梱されていませんが、microsoft マネージドデスクトップデバイス用にパッケージ化され、Microsoft によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="872f4-120">Teams is not shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="872f4-121">Azure Information Protection クライアントはデバイスに同梱されていませんが、展開用にパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="872f4-121">Azure Information Protection Client is not shipped with the device, but you can have this packaged for deployment.</span></span> 
<span data-ttu-id="872f4-122">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="872f4-122">Web Applications</span></span> |  <span data-ttu-id="872f4-123">Yammer、browser 内の Office、Delve、Flow、StaffHub、PowerApps、および Planner は、デバイスに同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="872f4-123">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner are not shipped with the device.</span></span> <span data-ttu-id="872f4-124">ユーザーは、ブラウザーを使用して、これらのアプリケーションの web バージョンにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="872f4-124">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="872f4-125">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="872f4-125">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="872f4-126">Application Virtualization (App-v)</span><span class="sxs-lookup"><span data-stu-id="872f4-126">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="872f4-127">Microsoft マネージドデスクトップでは、Microsoft Intune でサポートされていないため、この種類の展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="872f4-127">Microsoft Managed Desktop does not support this type of deployment as it is not supported by Microsoft Intune.</span></span>
<span data-ttu-id="872f4-128">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="872f4-128">Microsoft Defender Advanced Threat Protection</span></span> |  <span data-ttu-id="872f4-129">Microsoft マネージドデスクトップは、これを使用してデバイスのセキュリティを監視します。</span><span class="sxs-lookup"><span data-stu-id="872f4-129">Microsoft Managed Desktop uses this to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="872f4-130">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="872f4-130">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="872f4-131">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="872f4-131">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="872f4-132">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="872f4-132">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="872f4-133">Enterprise Mobility + Security E3 および Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="872f4-133">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="872f4-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="872f4-134">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="872f4-135">このオプション機能は、Microsoft マネージドデスクトップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="872f4-135">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="872f4-136">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="872f4-136">Azure Information Protection P2</span></span>  | <span data-ttu-id="872f4-137">このオプション機能は、Microsoft マネージドデスクトップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="872f4-137">You can use this optional feature with Microsoft Managed Desktop.</span></span>
