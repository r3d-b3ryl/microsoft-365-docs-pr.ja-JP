---
title: Windows 以外のプラットフォーム向け Microsoft Defender ATP
description: Windows 以外のプラットフォーム向け Microsoft Defender ATP 機能の詳細
keywords: Windows 以外、Mac、macos、Linux、android
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 64a19e9dd3d373c8092553ca9d60c711bfb500bc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186415"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="bf133-104">Microsoft Defender for Endpoint for Non-Windows プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="bf133-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf133-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bf133-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf133-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf133-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf133-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf133-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="bf133-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bf133-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf133-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="bf133-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bf133-110">Microsoft は、Windows と Windows Server を超えて業界をリードするエンドポイント セキュリティ機能を macOS、Linux、Android、およびまもなく iOS に拡張する取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="bf133-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and soon iOS.</span></span>

<span data-ttu-id="bf133-111">組織は、さまざまなプラットフォームやデバイス間で脅威に直面しています。</span><span class="sxs-lookup"><span data-stu-id="bf133-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="bf133-112">Microsoft のチームは *、Microsoft* だけでなく *Microsoft* からのセキュリティ ソリューションの構築にも取り組み、お客様が異種環境を保護し、セキュリティを確保できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="bf133-113">お客様からのフィードバックに耳を傾け、お客様のニーズに合ったソリューションを構築するために、お客様と密接に提携しています。</span><span class="sxs-lookup"><span data-stu-id="bf133-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="bf133-114">Microsoft Defender for Endpoint を使用すると、お客様は、Windows および Windows 以外のプラットフォーム全体で Microsoft Defender セキュリティ センターのすべての脅威とアラートを統合的に表示し、環境で何が起こっているかを完全に理解し、脅威の迅速な評価と対応を可能にします。</span><span class="sxs-lookup"><span data-stu-id="bf133-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="bf133-115">macOS 上のエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf133-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="bf133-116">Microsoft Defender for Endpoint on macOS では、最新リリースされた 3 つのバージョンの macOS に対して、ウイルス対策およびエンドポイント検出および応答 (EDR) 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf133-116">Microsoft Defender for Endpoint on macOS offers antivirus and endpoint detection and response (EDR) capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="bf133-117">お客様は、Microsoft Endpoint Manager と Jamf を使用してソリューションを展開および管理できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="bf133-118">macOS 上Microsoft Officeアプリケーションと同様に、Microsoft Auto Update を使用して Microsoft Defender for Endpoint on Mac 更新プログラムを管理します。</span><span class="sxs-lookup"><span data-stu-id="bf133-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="bf133-119">主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。</span><span class="sxs-lookup"><span data-stu-id="bf133-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="bf133-120">開始方法の詳細については、「Defender for Endpoint on macOS」のドキュメントを参照 [してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。</span><span class="sxs-lookup"><span data-stu-id="bf133-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>

## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="bf133-121">Microsoft Defender for Endpoint on Linux</span><span class="sxs-lookup"><span data-stu-id="bf133-121">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="bf133-122">Microsoft Defender for Endpoint on Linux では、Linux サーバーに対して予防 (AV) 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf133-122">Microsoft Defender for Endpoint on Linux offers preventative (AV) capabilities for Linux servers.</span></span> <span data-ttu-id="bf133-123">これには、エージェントの構成と管理、スキャンの開始、脅威の管理を行う完全なコマンド ライン エクスペリエンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf133-123">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="bf133-124">RHEL 7.2+、CentOS Linux 7.2+、Ubuntu 16 LTS、SLES 12+、Debian 9+、Oracle Linux 7.2 の 6 つの最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf133-124">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="bf133-125">Microsoft Defender for Endpoint on Linux は、Puppet、Ansible、または既存の Linux 構成管理ツールを使用して展開および構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-125">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="bf133-126">主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。</span><span class="sxs-lookup"><span data-stu-id="bf133-126">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="bf133-127">開始方法の詳細については、Microsoft Defender for Endpoint on Linux のドキュメントを参照 [してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux)。</span><span class="sxs-lookup"><span data-stu-id="bf133-127">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux).</span></span>

## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="bf133-128">Android 上のエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf133-128">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="bf133-129">Microsoft Defender for Endpoint on Android は、Android 6.0 以上を実行しているデバイス向けモバイル脅威防御ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="bf133-129">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="bf133-130">Android Enterprise (Work Profile) モードとデバイス管理者モードの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf133-130">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="bf133-131">Android では、フィッシング対策、安全でない接続のブロック、カスタムインジケーターの設定を含む Web 保護を提供しています。</span><span class="sxs-lookup"><span data-stu-id="bf133-131">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="bf133-132">このソリューションは、マルウェアや望ましくない可能性のあるアプリケーション (PUA) をスキャンし、Microsoft Endpoint Manager および条件付きアクセスとの統合を通じて、追加の侵害防止機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf133-132">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="bf133-133">主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。</span><span class="sxs-lookup"><span data-stu-id="bf133-133">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="bf133-134">開始方法の詳細については、Android の Microsoft Defender for Endpoint のドキュメントを参照 [してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-android)。</span><span class="sxs-lookup"><span data-stu-id="bf133-134">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-android).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="bf133-135">iOS 上のエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf133-135">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="bf133-136">Microsoft Defender for Endpoint on iOS は、iOS 11.0 以上を実行しているデバイス向けモバイル脅威防御ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="bf133-136">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="bf133-137">監視対象デバイスと教師付きデバイスの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf133-137">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="bf133-138">iOS では、フィッシング対策、安全でない接続のブロック、カスタムインジケーターの設定を含む Web 保護を提供しています。</span><span class="sxs-lookup"><span data-stu-id="bf133-138">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="bf133-139">主な機能と利点の詳細については、お知らせを [参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="bf133-139">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="bf133-140">開始方法の詳細については、iOS の Microsoft Defender for Endpoint のドキュメントを参照 [してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-ios)。</span><span class="sxs-lookup"><span data-stu-id="bf133-140">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-ios).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="bf133-141">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="bf133-141">Licensing requirements</span></span> 

<span data-ttu-id="bf133-142">対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-142">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="bf133-143">Microsoft Defender for Endpoint は、クラウド ソリューション プロバイダー (CSP) から購入できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-143">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="bf133-144">お客様は、Microsoft 365 A5/E5、または Microsoft 365 Security の一部として、スタンドアロンの Microsoft Defender for Endpoint ライセンスを通じて macOS 上の Microsoft Defender for Endpoint を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-144">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="bf133-145">最近発表された Microsoft Defender for Endpoint for Android および iOS の機能は、対象となるライセンスユーザー向け 5 つの認定デバイスの一部として、上記のオファーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bf133-145">Recently announced capabilities of Microsoft Defender for Endpoint for Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="bf133-146">Defender for Endpoint on Linux は、商用および教育の両方のお客様が利用できる Defender for Endpoint Server SKU を通じて利用できます。</span><span class="sxs-lookup"><span data-stu-id="bf133-146">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="bf133-147">料金と追加の適格性要件については、アカウント チームまたは CSP にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="bf133-147">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>
