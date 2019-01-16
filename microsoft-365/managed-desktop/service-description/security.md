---
title: Microsoft マネージド デスクトップのセキュリティ
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869624"
---
# <a name="security-in-microsoft-managed-desktop"></a><span data-ttu-id="8e507-103">Microsoft マネージド デスクトップのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8e507-103">Security in Microsoft Managed Desktop</span></span>

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

<span data-ttu-id="8e507-p101">Microsoft 管理デスクトップでは、標準的な一連のポリシーが適用され、管理されたデスクトップのマイクロソフトのセキュリティで保護されたデバイス、ストアドの会社データ、ために多くのマイクロソフトのテクノロジを利用しています。以下に示す領域がさらに詳細については。</span><span class="sxs-lookup"><span data-stu-id="8e507-p101">Microsoft Managed Desktop applies a standard set of policies and utilizes many Microsoft technologies to help secure Microsoft Managed Desktop devices, stored company data, and more. The areas listed below are detailed further:</span></span>  

- <span data-ttu-id="8e507-106">[データのセキュリティ](#data-security)- マイクロソフトの管理されたデスクトップとは、安全に保管によって収集されたデータの種類</span><span class="sxs-lookup"><span data-stu-id="8e507-106">[Data security](#data-security) - types of data collected by Microsoft Managed Desktop and where it's securely stored</span></span>
- <span data-ttu-id="8e507-107">[デバイスのセキュリティ](#device-security): セキュリティと管理されたデスクトップの Microsoft デバイスの保護</span><span class="sxs-lookup"><span data-stu-id="8e507-107">[Device security](#device-security) – security and protection on Microsoft Managed Desktop devices</span></span>
- <span data-ttu-id="8e507-108">Azure Active Directory id のサービスを通じて、デバイスの[id およびアクセス管理](#identity-and-access-management): セキュリティで保護された管理を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8e507-108">[Identity and Access Management](#identity-and-access-management) – managing secure use of devices through Azure Active Directory identity services</span></span>
- <span data-ttu-id="8e507-109">[ネットワーク セキュリティ](#network-security): VPN 情報と管理されたデスクトップのマイクロソフトの推奨ソリューションと設定</span><span class="sxs-lookup"><span data-stu-id="8e507-109">[Network security](#network-security) – VPN information and Microsoft Managed Desktop recommended solution and settings</span></span>
- <span data-ttu-id="8e507-110">[情報セキュリティ](#information-security): さらに機密情報を保護するためのオプションの使用可能なサービス</span><span class="sxs-lookup"><span data-stu-id="8e507-110">[Information security](#information-security) – optional available services to further protect sensitive information</span></span> 

## <a name="data-security"></a><span data-ttu-id="8e507-111">データ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8e507-111">Data security</span></span>

<span data-ttu-id="8e507-112">(これによって、Microsoft 管理デスクトップ IT サービスの操作)、テナントのお客様から収集されたデータは、アメリカ合衆国でホストされている Microsoft のテナントに Azure の SQL データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8e507-112">Data collected from customer tenants (which enables Microsoft Managed Desktop IT services and operations) is stored in Azure SQL databases in the Microsoft tenant hosted in the United States of America.</span></span>

<span data-ttu-id="8e507-113">詳細については、 [Microsoft Azure のセキュリティ](https://docs.microsoft.com/azure/security/azure-database-security-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e507-113">For more information, see [Microsoft Azure security](https://docs.microsoft.com/azure/security/azure-database-security-overview).</span></span>

<span data-ttu-id="8e507-114">次のとおり、テナントから送信されるデータの種類。</span><span class="sxs-lookup"><span data-stu-id="8e507-114">Listed below are the types of data transmitted from your tenant:</span></span>

- <span data-ttu-id="8e507-115">デバイスの更新プログラム、使用状況および信頼性データ</span><span class="sxs-lookup"><span data-stu-id="8e507-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="8e507-116">アプリケーションの展開と信頼性のデータ</span><span class="sxs-lookup"><span data-stu-id="8e507-116">App deployment and reliability data</span></span>
- <span data-ttu-id="8e507-117">更新プログラムとセキュリティ ポリシーの配置のデータ</span><span class="sxs-lookup"><span data-stu-id="8e507-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="8e507-118">デバイスに割り当てられているユーザー</span><span class="sxs-lookup"><span data-stu-id="8e507-118">Users assigned to devices</span></span>



## <a name="device-security"></a><span data-ttu-id="8e507-119">デバイスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8e507-119">Device security</span></span>

<span data-ttu-id="8e507-120">Microsoft 管理されたデスクトップは、すべての管理対象デバイスは、セキュリティで保護されてと保護され、次のサービスを使用してできるだけ早い段階で脅威を検出を保証します。</span><span class="sxs-lookup"><span data-stu-id="8e507-120">Microsoft Managed Desktop ensures all managed devices are secured and protected, and detects threats as early as possible using the following services:</span></span>

<span data-ttu-id="8e507-121">サービス</span><span class="sxs-lookup"><span data-stu-id="8e507-121">Service</span></span> | <span data-ttu-id="8e507-122">説明</span><span class="sxs-lookup"><span data-stu-id="8e507-122">Description</span></span>
--- | ---
<span data-ttu-id="8e507-123">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="8e507-123">Antivirus</span></span> | <span data-ttu-id="8e507-124">Windows Defender のウイルス対策のインストールし、構成</span><span class="sxs-lookup"><span data-stu-id="8e507-124">Windows Defender AV is installed and configured</span></span><br><span data-ttu-id="8e507-125">Windows Defender のウイルス対策定義が最新の状態</span><span class="sxs-lookup"><span data-stu-id="8e507-125">Windows Defender AV definitions are up to date</span></span>
<span data-ttu-id="8e507-126">フル ボリューム暗号化</span><span class="sxs-lookup"><span data-stu-id="8e507-126">Full Volume Encryption</span></span> |    <span data-ttu-id="8e507-127">Windows BitLocker は、マイクロソフトの管理されたデスクトップのデバイスのボリューム暗号化ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="8e507-127">Windows BitLocker is the volume encryption solution for Microsoft Managed Desktop devices.</span></span><br><br><span data-ttu-id="8e507-128">組織がサービスに onboarded と、デバイスはデバイスがスリープ モードに切り替える場合は、ローカル データに不正アクセスを防止するのには Windows BitLocker と組み込み信頼プラットフォーム モジュール (TPM) を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="8e507-128">Once an organization is onboarded into the service, devices will be encrypted using Windows BitLocker with built-in Trust Platform Module (TPM) to prevent unauthorized access to local data when the device is in sleep mode, or off.</span></span> 
<span data-ttu-id="8e507-129">"Monitoring/監視"</span><span class="sxs-lookup"><span data-stu-id="8e507-129">Monitoring</span></span> |    <span data-ttu-id="8e507-p102">Windows Defender 高度な脅威保護 (Windows Defender の ATP) は、マイクロソフトの管理されたデスクトップのすべてのデバイス間でセキュリティの脅威を監視するために使用されます。Windows Defender の分析ツールにより、企業を検出、調査、および企業ネットワーク内の高度な脅威に対応します。詳細についてを参照してください[の高度な脅威保護の Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 。</span><span class="sxs-lookup"><span data-stu-id="8e507-p102">Windows Defender Advanced Threat Protection (Windows Defender ATP) is used for security threat monitoring across all Microsoft Managed Desktop devices. Windows Defender ATP allows enterprise customers to detect, investigate, and respond to advanced threats in their corporate network. For more information, see [Windows Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span></span> 
<span data-ttu-id="8e507-133">ソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="8e507-133">Software updates</span></span> |  <span data-ttu-id="8e507-134">管理されたデスクトップの Microsoft のデバイスは、常に最新のセキュリティ更新プログラムとセキュリティで保護されています。</span><span class="sxs-lookup"><span data-stu-id="8e507-134">Microsoft Managed Desktop devices are always secured with the latest security updates.</span></span>
<span data-ttu-id="8e507-135">セキュリティで保護されたデバイスの構成</span><span class="sxs-lookup"><span data-stu-id="8e507-135">Secure Device Configuration</span></span> |   <span data-ttu-id="8e507-p103">Microsoft 管理されたデスクトップでは、マイクロソフトのセキュリティ ベースラインを実装します。詳細についてを参照してください[Windows セキュリティ ベースライン](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="8e507-p103">Microsoft Managed Desktop implements the Microsoft Security Baseline. For more information, see [Windows security baselines.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span></span>



## <a name="identity-and-access-management"></a><span data-ttu-id="8e507-138">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="8e507-138">Identity and access management</span></span>

<span data-ttu-id="8e507-p104">アイデンティティおよびアクセス管理では、企業の資産とビジネス ・ クリティカルなデータを保護します。Microsoft 管理されたデスクトップでは、Azure Active Directory (AD の Azure) の使用をセキュリティで保護されたユーザーを管理することを確認するデバイスを構成します。Azure AD テナント内の正確な情報を維持するためにお客様の責任です。</span><span class="sxs-lookup"><span data-stu-id="8e507-p104">Identity and access management protects corporate assets and business-critical data. Microsoft Managed Desktop configures devices to ensure secure use with Azure Active Directory (Azure AD) managed identities. It is the customer's responsibility to maintain accurate information in their Azure AD tenant.</span></span> 

<span data-ttu-id="8e507-142">サービス</span><span class="sxs-lookup"><span data-stu-id="8e507-142">Service</span></span> | <span data-ttu-id="8e507-143">説明</span><span class="sxs-lookup"><span data-stu-id="8e507-143">Description</span></span>
--- | ---
<span data-ttu-id="8e507-144">バイオ メトリック認証</span><span class="sxs-lookup"><span data-stu-id="8e507-144">Biometric Authentication</span></span> |  <span data-ttu-id="8e507-p105">Windows こんにちはでは、ユーザーが自分の顔や PIN、パスワードを忘れたり紛失したり、盗難が発生しにくくすることを使用してログインします。詳細についてを参照してください[Windows こんにちは](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)。</span><span class="sxs-lookup"><span data-stu-id="8e507-p105">Windows Hello allows users to login using their face or a PIN, making passwords harder to forget or steal. For more information, see [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span></span>
<span data-ttu-id="8e507-147">多要素認証</span><span class="sxs-lookup"><span data-stu-id="8e507-147">Multi-factor authentication</span></span> | <span data-ttu-id="8e507-148">Azure の多要素認証より緊密にも、セルフ サービス パスワード リセットとして、携帯電話を使用する認証のレベルを提供することによって管理されるデスクトップの Microsoft のサービスの重要な機能へのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="8e507-148">Azure multi-factor authentication more tightly controls access to sensitive functions of the Microsoft Managed Desktop service by providing an additional level of authentication using a mobile phone, as well as self-service password reset.</span></span> 
<span data-ttu-id="8e507-149">標準ユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8e507-149">Standard user permission</span></span> |  <span data-ttu-id="8e507-p106">システムを保護し、セキュリティを強化、ユーザーが割り当てられます標準ユーザーのアクセス許可。これは、Windows の自動操縦装置の標準のエクスペリエンスの一部として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8e507-p106">To protect the system and make it more secure, the user will be assigned Standard User Permissions. This is assigned as part of the Windows Autopilot out-of-box experience.</span></span>



## <a name="network-security"></a><span data-ttu-id="8e507-152">ネットワークのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8e507-152">Network security</span></span>

<span data-ttu-id="8e507-153">お客様は、ネットワークのセキュリティを担当します。</span><span class="sxs-lookup"><span data-stu-id="8e507-153">Customers are responsible for network security.</span></span> 

<span data-ttu-id="8e507-154">サービス</span><span class="sxs-lookup"><span data-stu-id="8e507-154">Service</span></span> | <span data-ttu-id="8e507-155">説明</span><span class="sxs-lookup"><span data-stu-id="8e507-155">Description</span></span>
--- | ---
<span data-ttu-id="8e507-156">VPN</span><span class="sxs-lookup"><span data-stu-id="8e507-156">VPN</span></span> | <span data-ttu-id="8e507-157">お客様は、イントラネットの外部企業の限られたリソースを公開することを確認するのには、VPN インフラストラクチャを所有します。</span><span class="sxs-lookup"><span data-stu-id="8e507-157">Customers own their VPN infrastructure, to ensure limited corporate resources can be exposed outside the intranet.</span></span><br><br><span data-ttu-id="8e507-p107">最低限の条件: Microsoft の管理されたデスクトップには、Windows 10 互換性があり、サポートされている VPN ソリューションが必要です。組織では、VPN ソリューションを必要とする場合は、10 の Windows をサポートしており、パッケージ、および Intune によって展開する必要があります。詳細については、ソフトウェアの発行元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8e507-p107">Minimum requirement: Microsoft Managed Desktop requires a Windows 10 compatible and supported VPN solution. If your organization needs a VPN solution, it needs to support Windows 10 and be packaged and deployable through Intune. Contact your software publisher for more information.</span></span><br><br><span data-ttu-id="8e507-161">に関する推奨事項:</span><span class="sxs-lookup"><span data-stu-id="8e507-161">Recommendation:</span></span><br><span data-ttu-id="8e507-p108">マイクロソフトは、Intune によってプッシュ VPN プロファイルを簡単に展開されている最新の VPN ソリューションをお勧めします。これは、企業ネットワークにアクセスするのには、常時、シームレスな信頼性、およびセキュリティで保護された方法を提供します。詳細については、 [[Intune での VPN 設定]](https://docs.microsoft.com/intune/vpn-settings-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e507-p108">- Microsoft recommends a modern VPN solution that could be easily deployed through Intune to push VPN profiles. This provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see [[VPN settings in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).</span></span><br><span data-ttu-id="8e507-165">-厚みの VPN クライアント、または従来の VPN クライアントでは、推奨されませんマイクロソフトによってエンドユーザーの環境に影響を与えることができます、マイクロソフトの管理されたデスクトップを使用しているときに。</span><span class="sxs-lookup"><span data-stu-id="8e507-165">- Thick VPN clients, or legacy VPN clients, are not recommended by Microsoft while using Microsoft Managed Desktop as it can impact the end-user environment.</span></span><br><span data-ttu-id="8e507-166">マイクロソフトでは、発信の web トラフィックのパフォーマンスの問題を回避するのには VPN を経由せずにインターネットに直接にはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8e507-166">- Microsoft recommends that the outgoing web traffic goes directly to Internet without going through the VPN to avoid any performance issues.</span></span><br><span data-ttu-id="8e507-167">-理想的には、Azure Active ディレクトリのアプリケーション プロキシ、VPN ではなくの使用を推奨します。</span><span class="sxs-lookup"><span data-stu-id="8e507-167">- Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</span></span>


## <a name="information-security"></a><span data-ttu-id="8e507-168">情報セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8e507-168">Information security</span></span>

<span data-ttu-id="8e507-169">お客様は、企業の付加価値の高い資産を保護するためにこれらのオプション サービスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8e507-169">Customers may configure these optional services to help protect corporate high-value assets.</span></span> 

<span data-ttu-id="8e507-170">サービス</span><span class="sxs-lookup"><span data-stu-id="8e507-170">Service</span></span> | <span data-ttu-id="8e507-171">説明</span><span class="sxs-lookup"><span data-stu-id="8e507-171">Description</span></span>
--- | ---
<span data-ttu-id="8e507-172">データ ・ リカバリ</span><span class="sxs-lookup"><span data-stu-id="8e507-172">Data recovery</span></span>  | <span data-ttu-id="8e507-p109">デバイス上のキーのフォルダーに格納された情報は、ビジネスの OneDrive にバックアップされます。Microsoft 管理されたデスクトップは、ビジネスのための OneDrive と同期されていないデータの責任ではありません。</span><span class="sxs-lookup"><span data-stu-id="8e507-p109">Information stored in key folders on the device is backed up to OneDrive for Business. Microsoft Managed Desktop is not responsible for data that isn’t synchronized with OneDrive for Business.</span></span> 
<span data-ttu-id="8e507-175">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="8e507-175">Windows Information Protection</span></span> |    <span data-ttu-id="8e507-176">[Windows の情報保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)をお勧め高いレベルの情報セキュリティを必要とする企業と[Azure 情報保護します。](https://www.microsoft.com/cloud-platform/azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="8e507-176">For companies that require high levels of information security, we recommend [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection).</span></span> 

