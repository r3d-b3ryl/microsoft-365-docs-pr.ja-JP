---
title: 管理されていない Windows 10 Pc および Mac を保護する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 を使用した、キャンペーンに対するフィッシングやその他の攻撃から保護します。
ms.openlocfilehash: 0cd96cb73ad3d0b38ab1e5ff31c913d97528c2d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632793"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="030e8-103">管理されていない Windows 10 Pc および Mac を保護する</span><span class="sxs-lookup"><span data-stu-id="030e8-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="030e8-104">Windows 10 Pc および Mac を Microsoft Intune に登録することによって管理できます。これにより、環境内のデータにアクセスする前に、それらを正常かつ安全な状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="030e8-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="030e8-105">しかし、多くのキャンペーンおよび小規模企業には、組織で管理されていない独自のデバイス (byod) を持っているスタッフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="030e8-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="030e8-106">これらの管理されていない Pc および Mac では、この記事を使用して最小限のセキュリティ機能が構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="030e8-107">Windows 10 または Mac を実行しているコンピューターを保護する</span><span class="sxs-lookup"><span data-stu-id="030e8-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="030e8-108">Windows 10 PC または Mac が組織で管理されていない場合は、必ずこれらのセキュリティ機能を構成してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="030e8-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="030e8-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="030e8-110">**デバイスの暗号化を有効にする**</span><span class="sxs-lookup"><span data-stu-id="030e8-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="030e8-111">デバイスの暗号化は、さまざまな Windows デバイスで使用でき、暗号化によってデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="030e8-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="030e8-112">デバイスの暗号化を有効にすると、承認されたユーザーのみがデバイスとデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="030e8-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="030e8-113">手順については、「 [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="030e8-114">デバイスの暗号化がデバイスで使用できない場合は、代わりに標準の[BitLocker 暗号化](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="030e8-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="030e8-115">(Windows 10 Home edition で BitLocker を使用することはできません。)</span><span class="sxs-lookup"><span data-stu-id="030e8-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="030e8-116">**Windows セキュリティを使用してデバイスを保護する**</span><span class="sxs-lookup"><span data-stu-id="030e8-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="030e8-117">Windows 10 を使用している場合は、Windows セキュリティによる最新のウイルス対策保護が得られます。</span><span class="sxs-lookup"><span data-stu-id="030e8-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="030e8-118">Windows 10 を初めて起動すると、Windows セキュリティがオンになり、マルウェア (悪意のあるソフトウェア)、ウイルス、およびセキュリティの脅威をスキャンすることにより、PC の保護が積極的に促進されます。</span><span class="sxs-lookup"><span data-stu-id="030e8-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="030e8-119">Windows セキュリティは、リアルタイム保護を使用して、PC でダウンロードまたは実行されたすべての情報をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="030e8-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="030e8-120">Windows Update は、PC の安全性を確保して脅威から保護するために、Windows セキュリティの更新プログラムを自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="030e8-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="030e8-121">以前のバージョンの Windows を使用していて、Microsoft Security Essentials を使用している場合は、Windows セキュリティに移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="030e8-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="030e8-122">詳細については、「 [Windows セキュリティでデバイスを保護](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="030e8-123">**Windows ファイアウォールを有効にする**</span><span class="sxs-lookup"><span data-stu-id="030e8-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="030e8-124">別のファイアウォールが有効になっている場合でも、Windows ファイアウォールを常に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="030e8-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="030e8-125">Windows ファイアウォールを無効にすると、デバイス (とネットワークがある場合は、そのデバイスが許可されていないアクセスに対して脆弱になることがあります。</span><span class="sxs-lookup"><span data-stu-id="030e8-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="030e8-126">手順について[は、「Windows ファイアウォールの有効化または無効化](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="030e8-127">Mac</span><span class="sxs-lookup"><span data-stu-id="030e8-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="030e8-128">**FileVault を使用して Mac ディスクを暗号化する**</span><span class="sxs-lookup"><span data-stu-id="030e8-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="030e8-129">ディスクの暗号化は、デバイスの紛失や盗難時にデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="030e8-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="030e8-130">FileVault の完全な暗号化によって、スタートアップディスクの情報に対する権限のないアクセスを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="030e8-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="030e8-131">手順については[、「Use FileVault to encrypt the startup disk In Mac](https://support.apple.com/HT204837) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="030e8-132">**マルウェアから mac を保護する**</span><span class="sxs-lookup"><span data-stu-id="030e8-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="030e8-133">Microsoft は、信頼性の高いウイルス対策ソフトウェアを Mac にインストールして使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="030e8-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="030e8-134">選択肢の一覧については、次の記事を参照してください。[最適な Mac ウイルス対策 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。</span><span class="sxs-lookup"><span data-stu-id="030e8-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="030e8-135">また、信頼できるソースからのソフトウェアのみを使用してマルウェアのリスクを軽減することもできます。</span><span class="sxs-lookup"><span data-stu-id="030e8-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="030e8-136">[セキュリティの & プライバシー設定] の設定では、Mac にインストールされているソフトウェアのソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="030e8-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="030e8-137">詳細については、「[マルウェアから Mac を保護](https://support.apple.com/kb/PH25087)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="030e8-138">**ファイアウォール保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="030e8-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="030e8-139">インターネットまたはネットワークに接続しているときに他のコンピューターによって開始された不要な連絡先から Mac を保護するには、ファイアウォールの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="030e8-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="030e8-140">この保護を使用しないと、Mac が権限のないアクセスに対して脆弱になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="030e8-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="030e8-141">手順に[ついては、「アプリケーションファイアウォールについ](https://support.apple.com/HT201642)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030e8-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
