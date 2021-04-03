---
title: Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する
description: 証明書の要件と Wi-Fi 接続
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574585"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a><span data-ttu-id="77f47-104">Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="77f47-104">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>  
 
<span data-ttu-id="77f47-105">証明書ベースの認証は、Microsoft Managed Desktop を使用しているお客様に共通の要件です。</span><span class="sxs-lookup"><span data-stu-id="77f47-105">Certificate-based authentication is a common requirement for customers using Microsoft Managed Desktop.</span></span> <span data-ttu-id="77f47-106">VPN ソリューションへの接続、または組織内Wi-Fiにアクセスするために、証明書が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="77f47-106">You might require certificates to access Wi-Fi or LAN, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>   
 
<span data-ttu-id="77f47-107">Microsoft Managed Desktop デバイスは Azure Active Directory (Azure AD) に参加し、Microsoft Intune によって管理されますので、Intune と統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、このような証明書を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77f47-107">Because Microsoft Managed Desktop devices are joined to Azure Active Directory (Azure AD) and are managed by Microsoft Intune, you must deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with Intune.</span></span>    
 
## <a name="certificate-requirements"></a><span data-ttu-id="77f47-108">証明書の要件</span><span class="sxs-lookup"><span data-stu-id="77f47-108">Certificate requirements</span></span> 
 
<span data-ttu-id="77f47-109">ルート証明書は、SCEP または PKCS インフラストラクチャを介して証明書を展開するために必要です。</span><span class="sxs-lookup"><span data-stu-id="77f47-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="77f47-110">組織内の他のアプリケーションとサービスでは、ルート証明書を Microsoft Managed Desktop デバイスに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77f47-110">Other applications and services in your organization might require root certificates to be deployed to your Microsoft Managed Desktop devices.</span></span>    
 
<span data-ttu-id="77f47-111">SCEP または PKCS 証明書を Microsoft Managed Desktop に展開する前に、組織内のユーザーまたはデバイス証明書を必要とする各サービスの要件を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77f47-111">Before you deploy SCEP or PKCS certificates to Microsoft Managed Desktop, you should gather requirements for each service that requires a user or device certificate in your organization.</span></span> <span data-ttu-id="77f47-112">このアクティビティを簡単にするために、次のいずれかの計画テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77f47-112">To make this activity easier, you can use one of the following planning templates:</span></span>  
 
- [<span data-ttu-id="77f47-113">PKCS 証明書テンプレート</span><span class="sxs-lookup"><span data-stu-id="77f47-113">PKCS certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [<span data-ttu-id="77f47-114">SCEP 証明書テンプレート</span><span class="sxs-lookup"><span data-stu-id="77f47-114">SCEP certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="77f47-115">Wi-Fiの要件</span><span class="sxs-lookup"><span data-stu-id="77f47-115">Wi-Fi connectivity requirements</span></span>

<span data-ttu-id="77f47-116">エンタープライズ ネットワークに必要な構成をデバイスに自動的にWi-Fiするには、構成プロファイルをWi-Fiがあります。</span><span class="sxs-lookup"><span data-stu-id="77f47-116">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you might need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="77f47-117">Microsoft Managed Desktop を構成して、これらのプロファイルをデバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="77f47-117">You can configure Microsoft Managed Desktop to deploy these profiles to your devices.</span></span> <span data-ttu-id="77f47-118">ネットワーク セキュリティでデバイスがローカル ドメインの一部である必要がある場合は、Wi-Fi ネットワーク インフラストラクチャを評価して Microsoft Managed Desktop デバイスと互換性を確認する必要があります (Microsoft マネージ デスクトップ デバイスは Azure AD に参加しているのみ)。</span><span class="sxs-lookup"><span data-stu-id="77f47-118">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with Microsoft Managed Desktop devices (Microsoft Managed Desktop devices are Azure AD-joined only).</span></span> 
 
<span data-ttu-id="77f47-119">Microsoft Managed Desktop デバイスにWi-Fi構成を展開する前に、ネットワークごとに組織の要件をWi-Fiされます。</span><span class="sxs-lookup"><span data-stu-id="77f47-119">Before you deploy a Wi-Fi configuration to Microsoft Managed Desktop devices, you will be required to gather your organization’s requirements for each Wi-Fi network.</span></span> <span data-ttu-id="77f47-120">このアクティビティを簡単にするために、この WiFi プロファイル テンプレート [を使用できます](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="77f47-120">To make this activity easier, you can use this [WiFi profile template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).</span></span>
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a><span data-ttu-id="77f47-121">有線接続要件と 802.1x 認証</span><span class="sxs-lookup"><span data-stu-id="77f47-121">Wired connectivity requirements and 802.1x authentication</span></span> 
 
<span data-ttu-id="77f47-122">802.1x 認証を使用してデバイスからローカル エリア ネットワーク (LAN) へのアクセスをセキュリティで保護する場合は、必要な構成の詳細を Microsoft Managed Desktop デバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77f47-122">If you use 802.1x authentication to secure access from devices to your local area network (LAN), you will need to push the required configuration details to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="77f47-123">Windows 10 バージョン 1809 以降を実行している Microsoft Managed Desktop デバイスは、WiredNetwork 構成サービス プロバイダー (CSP) を介した 802.1x 構成の展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="77f47-123">Microsoft Managed Desktop devices running Windows 10, version 1809 or later support deploying an 802.1x configuration through the WiredNetwork configuration service provider (CSP).</span></span> <span data-ttu-id="77f47-124">詳細については [、「WiredNetwork CSP のドキュメント」を参照](/windows/client-management/mdm/wirednetwork-csp) してください。</span><span class="sxs-lookup"><span data-stu-id="77f47-124">For more information, see [WiredNetwork CSP](/windows/client-management/mdm/wirednetwork-csp) documentation.</span></span> 
 
<span data-ttu-id="77f47-125">Microsoft Managed Desktop デバイスに有線ネットワーク構成プロファイルを展開する前に、組織の有線企業ネットワークの要件を収集してください。</span><span class="sxs-lookup"><span data-stu-id="77f47-125">Before you deploy a wired network configuration profile to Microsoft Managed Desktop devices, gather your organization’s requirements for your wired corporate network.</span></span> <span data-ttu-id="77f47-126">そのために、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="77f47-126">To do so, follow these steps:</span></span> 
 
 
1. <span data-ttu-id="77f47-127">既存の 802.1x プロファイルが構成され、LAN ネットワークに接続されているデバイスにサインオンします。</span><span class="sxs-lookup"><span data-stu-id="77f47-127">Sign on to a device that has your existing 802.1x profile configured and is connected to the LAN network.</span></span>  
2. <span data-ttu-id="77f47-128">管理者資格情報を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="77f47-128">Open a command prompt with administrative credentials.</span></span> 
3. <span data-ttu-id="77f47-129">netsh インターフェイス ショー インターフェイスを実行して **LAN インターフェイス名を検索します**。</span><span class="sxs-lookup"><span data-stu-id="77f47-129">Find the LAN interface name by running **netsh interface show interface**.</span></span> 
4. <span data-ttu-id="77f47-130">netsh lan エクスポート プロファイル フォルダー= を実行して **LAN プロファイル XML をエクスポートします。 Interface="interface_name" .**</span><span class="sxs-lookup"><span data-stu-id="77f47-130">Export the LAN profile XML by running **netsh lan export profile folder=.  Interface=”interface_name”**.</span></span> 
5. <span data-ttu-id="77f47-131">Microsoft Managed Desktop デバイスでエクスポートしたプロファイルをテストする必要がある場合は、netsh lan add profile **filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" を実行します**。</span><span class="sxs-lookup"><span data-stu-id="77f47-131">If you need to test your exported profile on Microsoft Managed Desktop device, run **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**.</span></span> 
 
 
## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="77f47-132">証明書インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="77f47-132">Deploy certificate infrastructure</span></span>  
 
<span data-ttu-id="77f47-133">Intune に既存の SCEP または PKCS インフラストラクチャが既に存在し、この方法が要件を満たしている場合は、Microsoft Managed Desktop でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="77f47-133">If you already have an existing SCEP or PKCS infrastructure with Intune and this approach meets your requirements, you can also use it for Microsoft Managed Desktop.</span></span> <span data-ttu-id="77f47-134">SCEP または PKCS インフラストラクチャが既に存在しない場合は、準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77f47-134">If no SCEP or PKCS infrastructure already exists, you'll have to prepare one.</span></span>  
 
<span data-ttu-id="77f47-135">詳細については [、「Microsoft Intune でデバイスの証明書プロファイルを構成する」を参照してください](/intune/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="77f47-135">For more information, see [Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure).</span></span> 
 
 
 
## <a name="deploy-a-lan-profile"></a><span data-ttu-id="77f47-136">LAN プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="77f47-136">Deploy a LAN profile</span></span> 
 
<span data-ttu-id="77f47-137">LAN プロファイルをエクスポートしたら、次の手順に従って Microsoft Managed Desktop のポリシーを準備できます。</span><span class="sxs-lookup"><span data-stu-id="77f47-137">Once your LAN profile has been exported, you can prepare the policy for Microsoft Managed Desktop by following these steps:</span></span>   
 
1. <span data-ttu-id="77f47-138">次の設定を使用して、LAN プロファイルの Microsoft Intune でカスタム プロファイルを作成します (「Intune で [Windows 10](/intune/custom-settings-windows-10)デバイスのカスタム設定を使用する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="77f47-138">Create a custom profile in Microsoft Intune for the LAN profile using the following settings (see [Use custom settings for Windows 10 devices in Intune](/intune/custom-settings-windows-10)).</span></span> <span data-ttu-id="77f47-139">[**カスタム OMA-URI 設定] で、[\*\*\*\*追加]** を選択し、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="77f47-139">In **Custom OMA-URI Settings**, select **Add**, and then enter the following values:</span></span> 
    - <span data-ttu-id="77f47-140">名前: *モダン Workplace-Windows 10 LAN プロファイル*</span><span class="sxs-lookup"><span data-stu-id="77f47-140">Name: *Modern Workplace-Windows 10 LAN Profile*</span></span> 
    - <span data-ttu-id="77f47-141">説明: 設定の概要、その他の重要な詳細を示す説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="77f47-141">Description: Enter a description that gives an overview of the setting, and any other important details.</span></span> 
    - <span data-ttu-id="77f47-142">OMA-URI (大文字と小文字の区別): *Enter ./Device/Vendor/MSFT/WiredNetwork/LanXML*</span><span class="sxs-lookup"><span data-stu-id="77f47-142">OMA-URI (case sensitive): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*</span></span>
    - <span data-ttu-id="77f47-143">データ型: [文字列] **(XML ファイル) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="77f47-143">Data type: select **String (XML file)**.</span></span> 
    - <span data-ttu-id="77f47-144">カスタム XML: エクスポートされた XML ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="77f47-144">Custom XML: Upload the exported XML file.</span></span>
2. <span data-ttu-id="77f47-145">Microsoft Managed Desktop Admin ポータルを使用して Microsoft Managed Desktop IT 操作にサポート要求を送信し、構成プロファイルを "モダン ワークプレース デバイス - テスト" に確認して展開します。</span><span class="sxs-lookup"><span data-stu-id="77f47-145">Submit a Support request to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="77f47-146">Microsoft Managed Desktop IT Operations は、管理ポータルのサポート要求を介して要求が完了した場合に知らせします。</span><span class="sxs-lookup"><span data-stu-id="77f47-146">Microsoft Managed Desktop IT Operations will let you know when the request is completed via the Support request in the Admin portal.</span></span>
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="77f47-147">証明書と Wi-Fi/VPN プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="77f47-147">Deploy certificates and Wi-Fi/VPN profile</span></span> 
 
 
<span data-ttu-id="77f47-148">証明書とプロファイルを展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77f47-148">To deploy certificates and profiles, follow these steps:</span></span>

1. <span data-ttu-id="77f47-149">ルート証明書と中間証明書のそれぞれについてプロファイルを作成します (「信頼できる証明書プロファイルの作成 [」を参照してください](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。</span><span class="sxs-lookup"><span data-stu-id="77f47-149">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles).</span></span> <span data-ttu-id="77f47-150">これらの各プロファイルには、DD/MM/YYYYY 形式の有効期限を含む説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="77f47-150">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="77f47-151">**有効期限のない証明書プロファイルは展開されません。**</span><span class="sxs-lookup"><span data-stu-id="77f47-151">**Certificate profiles without an expiration date will not be deployed.**</span></span>
2. <span data-ttu-id="77f47-152">SCEP または PKCS 証明書ごとにプロファイルを作成します [(「SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 証明書プロファイルを作成する」または [「PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)証明書プロファイルを作成する」を参照) これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="77f47-152">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or [Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="77f47-153">**有効期限のない証明書プロファイルは展開されません。**</span><span class="sxs-lookup"><span data-stu-id="77f47-153">**Certificate profiles without an expiration date will not be deployed.**</span></span>
3. <span data-ttu-id="77f47-154">企業の WiFi ネットワークごとにプロファイルを作成します (「Windows 10 以降のデバイスの[Wi-Fi 設定」を参照)。](/intune/wi-fi-settings-windows)</span><span class="sxs-lookup"><span data-stu-id="77f47-154">Create a profile for each corporate WiFi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span>
4. <span data-ttu-id="77f47-155">企業 VPN ごとにプロファイルを作成します (Intune を使用して VPN 接続を追加するには [、「Windows 10 と Windows Holographic デバイスの設定」を参照してください](/intune/vpn-settings-windows-10))。</span><span class="sxs-lookup"><span data-stu-id="77f47-155">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/intune/vpn-settings-windows-10)).</span></span>
5. <span data-ttu-id="77f47-156">Microsoft Managed Desktop Admin ポータルを使用して Microsoft Managed Desktop IT 運用に「証明書の展開」または「Wi-Fi プロファイルの展開」というタイトルのサポート要求を送信し、構成プロファイルを確認し、"モダン Workplace デバイス - テスト" に展開します。</span><span class="sxs-lookup"><span data-stu-id="77f47-156">Submit a Support request titled “Certificate Deployment” or “Wi-Fi Profile Deployment” to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="77f47-157">Microsoft Managed Desktop IT Operations は、管理ポータルのサポート要求を介して要求が完了した時間を知らせします。</span><span class="sxs-lookup"><span data-stu-id="77f47-157">Microsoft Managed Desktop IT Operations will let you know when the request has been completed via the Support request in the Admin portal.</span></span> 
 
## <a name="steps-to-get-ready"></a><span data-ttu-id="77f47-158">準備の手順</span><span class="sxs-lookup"><span data-stu-id="77f47-158">Steps to get ready</span></span>

1. <span data-ttu-id="77f47-159">「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="77f47-159">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="77f47-160">準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="77f47-160">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="77f47-161">ゲスト アカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="77f47-161">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="77f47-162">Microsoft マネージド デスクトップのネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="77f47-162">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. <span data-ttu-id="77f47-163">[Microsoft Managed Desktop 用の証明書とネットワーク プロファイルを準備](certs-wifi-lan.md) する (この記事)</span><span class="sxs-lookup"><span data-stu-id="77f47-163">[Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md) (This article)</span></span>
6. [<span data-ttu-id="77f47-164">Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="77f47-164">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="77f47-165">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="77f47-165">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="77f47-166">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="77f47-166">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="77f47-167">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="77f47-167">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md) 
