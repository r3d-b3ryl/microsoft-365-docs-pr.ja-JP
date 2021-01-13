---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、Microsoft マネージド デスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840903"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="38bf8-104">Microsoft マネージド デスクトップのテクノロジ</span><span class="sxs-lookup"><span data-stu-id="38bf8-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="38bf8-105">この記事では、Microsoft マネージド デスクトップで使用されるテクノロジとアプリの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="38bf8-105">This article lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="38bf8-106">Microsoft 365 Enterprise ライセンスは、すべての Microsoft マネージド デスクトップ ユーザーに必要です。</span><span class="sxs-lookup"><span data-stu-id="38bf8-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="38bf8-107">サービスのライセンス要件の詳細については、「Microsoft マネージド デスクトップの前提条件」 [を参照してください](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf8-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="38bf8-108">この記事では、必要なエンタープライズ ライセンスに含まれるコンポーネントの概要と、サービスが Microsoft マネージド デスクトップ デバイスで各コンポーネントを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38bf8-108">This article summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38bf8-109">各領域の特定の役割と責任については、Microsoft マネージド デスクトップのドキュメント全体で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="38bf8-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="38bf8-110">Office 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="38bf8-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="38bf8-111">Microsoft 365 Apps for enterprise (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="38bf8-111">Microsoft 365 Apps for enterprise (64-bit)</span></span> | <span data-ttu-id="38bf8-112">これらのOffice、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote のデバイスに同梱されます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="38bf8-113">64 ビット版の Microsoft Project および Microsoft Visio は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="38bf8-113">The 64-bit full versions of Microsoft Project and Microsoft Visio aren't included.</span></span> <span data-ttu-id="38bf8-114">ただし、これらのアプリケーションのインストールは Microsoft 365 Apps for enterprise インストールに依存します。このため、Microsoft マネージド デスクトップでは、ライセンスを取得したユーザーにこれらのアプリケーションを展開するために使用できる既定の Microsoft Intune 展開とセキュリティ グループが作成されています。</span><span class="sxs-lookup"><span data-stu-id="38bf8-114">However, since the installation of these applications depends on the Microsoft 365 Apps for enterprise installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed users.</span></span> <span data-ttu-id="38bf8-115">詳細については、「Microsoft マネージ デスクトップ デバイスへの [Microsoft Project または Microsoft Visio のインストール」を参照してください](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf8-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="38bf8-116">OneDrive</span><span class="sxs-lookup"><span data-stu-id="38bf8-116">OneDrive</span></span> |<span data-ttu-id="38bf8-117">Azure Active Directory シングル サインオンは、ユーザーが初めて OneDrive にサインインするときに有効になります。</span><span class="sxs-lookup"><span data-stu-id="38bf8-117">Azure Active Directory Single Sign On is enabled for users when they first sign in to OneDrive.</span></span><br><br><span data-ttu-id="38bf8-118">"Desktop"、"Document"、および "Pictures" フォルダーの既知のフォルダー リダイレクトが含まれます。有効にし、Microsoft マネージド デスクトップによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span>
<span data-ttu-id="38bf8-119">ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="38bf8-119">Store Apps</span></span> |    <span data-ttu-id="38bf8-120">Microsoft Sway と Power BI はデバイスに同梱されません。</span><span class="sxs-lookup"><span data-stu-id="38bf8-120">Microsoft Sway and Power BI aren't shipped with the device.</span></span> <span data-ttu-id="38bf8-121">これらのアプリは、Microsoft Store からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="38bf8-122">Win32 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="38bf8-122">Win32 Applications</span></span> |    <span data-ttu-id="38bf8-123">Teams はデバイスに同梱されませんが、Microsoft マネージド デスクトップ デバイス用に Microsoft によってパッケージ化および提供されます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-123">Teams isn't shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38bf8-124">Azure Information Protection クライアントはデバイスに同梱されませんが、展開用にパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-124">Azure Information Protection Client isn't shipped with the device, but you can have it packaged for deployment.</span></span>
<span data-ttu-id="38bf8-125">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="38bf8-125">Web Applications</span></span> |  <span data-ttu-id="38bf8-126">Yammer、Office Delve、Flow、StaffHub、PowerApps、Planner はデバイスに同梱されません。</span><span class="sxs-lookup"><span data-stu-id="38bf8-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner aren't shipped with the device.</span></span> <span data-ttu-id="38bf8-127">ユーザーはブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="38bf8-128">Windows 10 Enterprise E5 または E3 と Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="38bf8-128">Windows 10 Enterprise E5 or E3 with Microsoft Defender for Endpoint</span></span>

 |
 --- | ---
<span data-ttu-id="38bf8-129">Application Virtualization (App-V)</span><span class="sxs-lookup"><span data-stu-id="38bf8-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="38bf8-130">お客様は、Intune Win32 アプリ管理クライアントを使用して App-V パッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="38bf8-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="38bf8-131">Microsoft Defender for Endpoint</span></span> |    <span data-ttu-id="38bf8-132">Microsoft マネージド デスクトップは、この製品を使用してデバイスのセキュリティを監視します。</span><span class="sxs-lookup"><span data-stu-id="38bf8-132">Microsoft Managed Desktop uses this product to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="38bf8-133">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="38bf8-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="38bf8-134">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="38bf8-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="38bf8-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="38bf8-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="38bf8-136">Enterprise Mobility + Security E3 と Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="38bf8-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="38bf8-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="38bf8-138">このオプション機能は、Microsoft マネージド デスクトップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="38bf8-139">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="38bf8-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="38bf8-140">このオプション機能は、Microsoft マネージド デスクトップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="38bf8-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
