---
title: Microsoft 管理デスクトップ テクノロジ
description: このトピックには、テクノロジと Microsoft の管理されたデスクトップで使用されているアプリケーションが一覧表示されます。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 4b26ec88e1f4ca95fee6f7c4c927fc06cab32135
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869204"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="bdd9e-104">Microsoft 管理デスクトップ テクノロジ</span><span class="sxs-lookup"><span data-stu-id="bdd9e-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="bdd9e-105">このトピックには、テクノロジと Microsoft の管理されたデスクトップで使用されているアプリケーションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="bdd9e-p101">Microsoft 365 E5 ライセンス (またはそれと同等) は、管理されたデスクトップの Microsoft のサービスに必要です。このライセンスおよび管理されたデスクトップのマイクロソフトがマイクロソフトの管理されたデスクトップ デバイスと各コンポーネントを使用する方法に含まれるすべてのコンポーネントを次に示します。 各領域の特定の役割と責任はマイクロソフトの管理されたデスクトップのトピックで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p101">Microsoft 365 E5 License (or equivalent) is required for Microsoft Managed Desktop service. The following are all components that are included in this license and how Microsoft Managed Desktop uses each component with Microsoft Managed Desktop devices.  Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop topics.</span></span> 

<span data-ttu-id="bdd9e-109">Microsoft 365 E5 は、3 つのコンポーネントで構成されています: Office 365 の E5、10 企業の Windows と E5、エンタープライズ モビリティ + セキュリティ E5 します。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-109">Microsoft 365 E5 is comprised of 3 components: Office 365 E5, Windows 10 Enterprise and E5, Enterprise Mobility + Security E5.</span></span>  

## <a name="office-365-e5"></a><span data-ttu-id="bdd9e-110">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="bdd9e-110">Office 365 E5</span></span>
 |
 --- | ---
<span data-ttu-id="bdd9e-111">Office 365 の標準的なスイート (64 ビット) \*</span><span class="sxs-lookup"><span data-stu-id="bdd9e-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="bdd9e-112">デバイスとアプリケーションの標準的な Office スイートが出荷されます。 Word、Excel、PowerPoint、Outlook、Publisher、アクセス、ビジネス、OneNote の Skype です。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="bdd9e-p102">64 ビットの実行をクリックして Microsoft Project および Microsoft Visio の完全バージョンを (C2R) は、Office 365 の標準的なスイートでは含まれません。 ただし、これらのアプリケーションのインストールが標準の Office スイートのインストールに依存するため、Microsoft の管理されたデスクトップが作成既定 Intune 展開し、これらのアプリケーションを展開するお客様が使用するセキュリティ グループエンド ・ ユーザーのライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p102">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.  However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="bdd9e-115">ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="bdd9e-115">Store Apps</span></span> |    <span data-ttu-id="bdd9e-p103">マイクロソフト支配下に置いた、マイクロソフトのチーム、BI デスクトップの電源 (はない) に付属していないデバイスです。これらのアプリケーションは、Microsoft ストアからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p103">Microsoft Sway, Microsoft Teams, Power BI Desktop (not Pro) are not shipped with device. These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="bdd9e-118">Win32 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bdd9e-118">Win32 Applications</span></span> |    <span data-ttu-id="bdd9e-119">電源双 Pro、Azure 情報保護クライアント、および Microsoft の計画は、デバイスに付属していないと、お客様が配置のパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="bdd9e-120">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bdd9e-120">Web Applications</span></span> |  <span data-ttu-id="bdd9e-p104">Yammer、Delve、Office オンラインのフロー、StaffHub、PowerApps は、デバイスに付属していません。ユーザーは、web ブラウザーを使用してこれらのアプリケーションのバージョンにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p104">Yammer, Office Online, Delve, Flow, StaffHub, PowerApps are not shipped with the device. Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="bdd9e-123">ビジネス オンライン クラウド PBX の Skype</span><span class="sxs-lookup"><span data-stu-id="bdd9e-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="bdd9e-p105">この機能は、Office 365 の E5 を使用します。Microsoft 管理されたデスクトップはこのサービスのすべての側面を構成していません。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p105">This feature is available via Office 365 E5. Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="bdd9e-126">10 の Windows エンタープライズ E5</span><span class="sxs-lookup"><span data-stu-id="bdd9e-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="bdd9e-127">資格情報の保護</span><span class="sxs-lookup"><span data-stu-id="bdd9e-127">Credential Guard</span></span> |  <span data-ttu-id="bdd9e-128">Microsoft 管理されたデスクトップ、ガイダンスを用意し、この機能をクラウドの側面を管理</span><span class="sxs-lookup"><span data-stu-id="bdd9e-128">Microsoft Managed Desktop will provide guidance and manage cloud aspects of this feature</span></span>
<span data-ttu-id="bdd9e-129">デバイス保護 (Windows Defender のアプリケーションのコントロール)</span><span class="sxs-lookup"><span data-stu-id="bdd9e-129">Device Guard (Windows Defender Application Control)</span></span> | <span data-ttu-id="bdd9e-p106">Microsoft 管理されたデスクトップでは、ポリシーを作成します。顧客では、署名を管理します。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p106">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="bdd9e-132">AppLocker の管理</span><span class="sxs-lookup"><span data-stu-id="bdd9e-132">AppLocker management</span></span> |  <span data-ttu-id="bdd9e-p107">Microsoft 管理されたデスクトップでは、ポリシーを作成します。顧客では、署名を管理します。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p107">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="bdd9e-135">アプリケーションの仮想化 (APP-V)</span><span class="sxs-lookup"><span data-stu-id="bdd9e-135">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="bdd9e-136">Microsoft 管理デスクトップがこの種類の展開をサポートしていません Intune でサポートされていないようです。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-136">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="bdd9e-137">ユーザー エクスペリエンスの仮想化 (UE V)</span><span class="sxs-lookup"><span data-stu-id="bdd9e-137">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="bdd9e-138">管理 Microsoft 管理デスクトップ デバイスとこれは、使用できません。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-138">This is not used with Microsoft Managed Desktop managed devices</span></span>
<span data-ttu-id="bdd9e-139">管理のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="bdd9e-139">Managed User Experience</span></span>  | <span data-ttu-id="bdd9e-p108">これはデバイスの管理 Microsoft 管理されたデスクトップでは使用されません。MDM は、デバイス管理のソリューションとして使用します。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-p108">This is not used with Microsoft Managed Desktop managed devices. MDM is used as a solution for device management</span></span>
<span data-ttu-id="bdd9e-142">Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bdd9e-142">Windows Defender Advanced Threat Protection</span></span> |   <span data-ttu-id="bdd9e-143">デバイスのセキュリティ ポリシーを管理する Microsoft 管理されたデスクトップで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-143">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security"></a><span data-ttu-id="bdd9e-144">Enterprise Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="bdd9e-144">Enterprise Mobility + Security</span></span> 

 |
 --- | ---
<span data-ttu-id="bdd9e-145">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="bdd9e-145">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="bdd9e-146">Azure Active Directory プレミアム P2</span><span class="sxs-lookup"><span data-stu-id="bdd9e-146">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="bdd9e-147">MDM のデバイスを管理するエンタープライズ モビリティとセキュリティの E3 と AADP のすべての側面を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-147">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices</span></span>
<span data-ttu-id="bdd9e-148">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bdd9e-148">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="bdd9e-149">これは、管理されたデスクトップの Microsoft のサービスを顧客が使用できるオプション機能です。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-149">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="bdd9e-150">Azure の情報保護の P2</span><span class="sxs-lookup"><span data-stu-id="bdd9e-150">Azure Information Protection P2</span></span>  |<span data-ttu-id="bdd9e-151">これは、管理されたデスクトップの Microsoft のサービスを顧客が使用できるオプション機能です。</span><span class="sxs-lookup"><span data-stu-id="bdd9e-151">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
