---
title: 非管理対象の Windows 10 PC と Mac を保護する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 管理されていないデバイスまたは持ち込み専用デバイス (BYOD) を保護するには、Microsoft 365。
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398255"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="7bb80-103">非管理対象の Windows 10 PC と Mac を保護する</span><span class="sxs-lookup"><span data-stu-id="7bb80-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="7bb80-104">Windows 10 PC と Mac は、Microsoft Intune に登録することで管理できます。これにより、環境内のデータにアクセスする前に、正常で安全な状態を確保できます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="7bb80-105">ただし、多くのキャンペーンや小規模企業には、組織によって管理されない独自のデバイス (BYOD) を持ち込むスタッフが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="7bb80-106">これらの管理されていない PC および Mac については、この記事を使用して、最小限のセキュリティ機能が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bb80-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="7bb80-107">コンピューターまたは Mac をWindows 10するコンピューターを保護する</span><span class="sxs-lookup"><span data-stu-id="7bb80-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="7bb80-108">PC または mac Windows 10組織が管理していない場合は、必ずこれらのセキュリティ機能を構成してください。</span><span class="sxs-lookup"><span data-stu-id="7bb80-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="7bb80-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7bb80-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="7bb80-110">**デバイスの暗号化を有効にする**</span><span class="sxs-lookup"><span data-stu-id="7bb80-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="7bb80-111">デバイスの暗号化は、さまざまなデバイスで利用Windows、データを暗号化することでデータを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="7bb80-112">デバイスの暗号化を有効にした場合、承認された個人のみがデバイスとデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="7bb80-113">手順 [については、「デバイスの暗号化を有効](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb80-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="7bb80-114">デバイスでデバイスの暗号化を利用できない場合は、代わりに標準の暗号化[BitLocker有効](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)にできます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="7bb80-115">(BitLockerエディションでは使用Windows 10 Homeできません)。</span><span class="sxs-lookup"><span data-stu-id="7bb80-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="7bb80-116">**デバイスを保護するには、Windows セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="7bb80-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="7bb80-117">インストールされている場合Windows 10、最新のウイルス対策保護が提供Windows セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="7bb80-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="7bb80-118">Windows 10 を初めて起動すると、Windows セキュリティ が有効で、マルウェア (悪意のあるソフトウェア)、ウイルス、セキュリティの脅威をスキャンして PC を保護するために積極的に支援します。</span><span class="sxs-lookup"><span data-stu-id="7bb80-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="7bb80-119">Windows セキュリティリアルタイム保護を使用して、PC でダウンロードまたは実行するすべてをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="7bb80-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="7bb80-120">Windows Update では、自動的に Windows セキュリティの更新プログラムをダウンロードして、PC の安全を確保し、脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="7bb80-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="7bb80-121">以前のバージョンの Windowsを使用している場合Microsoft Security Essentialsに移動するとWindows セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="7bb80-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="7bb80-122">詳細については、「デバイスを保護[する」を参照Windows セキュリティ。](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="7bb80-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="7bb80-123">**ファイアウォールのWindowsする**</span><span class="sxs-lookup"><span data-stu-id="7bb80-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="7bb80-124">別のファイアウォールを有効Windows場合でも、常にファイアウォールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb80-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="7bb80-125">ファイアウォールをWindowsすると、デバイス (およびネットワークがある場合) が、承認されていないアクセスに対してより脆弱になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7bb80-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="7bb80-126">手順[については、「Windowsファイアウォールを有効または無効にする](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb80-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions.</span></span>

## <a name="mac"></a>[<span data-ttu-id="7bb80-127"> Mac </span><span class="sxs-lookup"><span data-stu-id="7bb80-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="7bb80-128">**FileVault を使用して Mac ディスクを暗号化する**</span><span class="sxs-lookup"><span data-stu-id="7bb80-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="7bb80-129">ディスク暗号化は、デバイスが紛失または盗難に遭った場合にデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="7bb80-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="7bb80-130">FileVault のフル ディスク暗号化は、起動ディスク上の情報への不正アクセスを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="7bb80-131">手順 [については、「FileVault を使用して](https://support.apple.com/HT204837) Mac 上の起動ディスクを暗号化する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb80-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="7bb80-132">**マルウェアから Mac を保護する**</span><span class="sxs-lookup"><span data-stu-id="7bb80-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="7bb80-133">Microsoft では、Mac に信頼性の高いウイルス対策ソフトウェアをインストールして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb80-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="7bb80-134">選択肢の一覧については、次の記事を参照してください。 [ベスト Mac ウイルス対策 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。</span><span class="sxs-lookup"><span data-stu-id="7bb80-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="7bb80-135">また、信頼できるソースからのみソフトウェアを使用することで、マルウェアのリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="7bb80-136">[セキュリティとプライバシー] &設定を使用すると、Mac にインストールされているソフトウェアのソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7bb80-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="7bb80-137">詳細については、「Mac を [マルウェアから保護する」を参照してください](https://support.apple.com/kb/PH25087)。</span><span class="sxs-lookup"><span data-stu-id="7bb80-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="7bb80-138">**ファイアウォール保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="7bb80-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="7bb80-139">ファイアウォールの設定を使用して、インターネットやネットワークに接続するときに他のコンピューターによって開始された不要な連絡先から Mac を保護します。</span><span class="sxs-lookup"><span data-stu-id="7bb80-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="7bb80-140">この保護がない場合、Mac は不正アクセスに対してより脆弱になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7bb80-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="7bb80-141">手順 [については、アプリケーション ファイアウォール](https://support.apple.com/HT201642) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb80-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
