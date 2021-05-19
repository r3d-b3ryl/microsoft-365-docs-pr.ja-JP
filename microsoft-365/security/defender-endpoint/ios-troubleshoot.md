---
title: iOS 上の Microsoft Defender for Endpoint の問題のトラブルシューティング
description: トラブルシューティングと FAQ - Microsoft Defender for Endpoint on iOS
keywords: microsoft、defender、Microsoft Defender for Endpoint、ios、トラブルシューティング、FAQ、方法
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82a3fcc58b97f53f584befae77c86e8a18952a23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539325"
---
# <a name="troubleshoot-issues-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="4bfb5-104">iOS 上の Microsoft Defender for Endpoint の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4bfb5-104">Troubleshoot issues on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4bfb5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4bfb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="4bfb5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4bfb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4bfb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bfb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4bfb5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4bfb5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4bfb5-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="4bfb5-110">このトピックでは、iOS で Microsoft Defender for Endpoint を使用する際に発生する可能性のある問題に対処するためのトラブルシューティング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="4bfb5-111">iOS 上のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="4bfb5-112">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="4bfb5-113">VPN が有効になっているとアプリが動作しない</span><span class="sxs-lookup"><span data-stu-id="4bfb5-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="4bfb5-114">アクティブな VPN が検出されると、機能を停止するアプリがあります。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="4bfb5-115">このようなアプリを使用している間は、VPN を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="4bfb5-116">既定では、Defender for Endpoint on iOS には Web 保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="4bfb5-117">[Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="4bfb5-118">iOS のエンドポイントの Defender は、この保護を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="4bfb5-119">これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="4bfb5-120">既定で有効になっている場合は、VPN を無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="4bfb5-121">たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="4bfb5-122">このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="4bfb5-123">iOS デバイスで、アプリを開き **設定[全般**] をクリック **またはタップ** し **、[VPN] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="4bfb5-124">Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="4bfb5-125">VPN を無効 **にするにはConnectをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4bfb5-126">![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="4bfb5-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="4bfb5-127">VPN が無効になっている場合、Web 保護は使用できません。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="4bfb5-128">Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="4bfb5-129">複数の VPN プロファイルに関する問題</span><span class="sxs-lookup"><span data-stu-id="4bfb5-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="4bfb5-130">Apple iOS では、同時にアクティブになる複数のデバイス全体の VPN はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="4bfb5-131">デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="4bfb5-132">バッテリー消費</span><span class="sxs-lookup"><span data-stu-id="4bfb5-132">Battery consumption</span></span>

<span data-ttu-id="4bfb5-133">アプリによるバッテリー使用量は、CPU やネットワークの使用状況など、さまざまな要因に基づいて Apple によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="4bfb5-134">Microsoft Defender for Endpoint では、バックグラウンドでローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="4bfb5-135">任意のアプリからのネットワーク パケットは、このチェックを通過し、Microsoft Defender for Endpoint のバッテリー使用量が不正確に計算される原因になります。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="4bfb5-136">これは、ユーザーに誤った印象を与えます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-136">This gives a false impression to the user.</span></span> <span data-ttu-id="4bfb5-137">Microsoft Defender for Endpoint の実際のバッテリー消費量は、デバイスの [バッテリー] ページに表示設定より小さいです。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="4bfb5-138">これは、バッテリー消費を理解するために Microsoft Defender for Endpoint アプリで実施されたテストに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="4bfb5-139">また、使用される VPN はローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="4bfb5-140">データの使用状況</span><span class="sxs-lookup"><span data-stu-id="4bfb5-140">Data usage</span></span>

<span data-ttu-id="4bfb5-141">Microsoft Defender for Endpoint では、ローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="4bfb5-142">このため、Apple は Microsoft Defender for Endpoint へのデータ使用量を不正確にアカウントします。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="4bfb5-143">Microsoft Defender for Endpoint による実際のデータ使用量は、デバイス上のデータ使用量のデータ使用量に表示されるデータ使用量設定はるかに小さい値です。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="4bfb5-144">安全でないサイトを報告する</span><span class="sxs-lookup"><span data-stu-id="4bfb5-144">Report unsafe site</span></span>

<span data-ttu-id="4bfb5-145">フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="4bfb5-146">[ネットワーク [保護に関するフィードバックを提供する](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) ] ページにアクセスして、フィッシング サイトになる可能性のある Web サイトを報告します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="4bfb5-147">悪意のあるサイトが検出されました</span><span class="sxs-lookup"><span data-stu-id="4bfb5-147">Malicious site detected</span></span>

<span data-ttu-id="4bfb5-148">Microsoft Defender for Endpoint は、フィッシングなどの Web ベースの攻撃からユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="4bfb5-149">悪意のあるサイトが検出されると、接続がブロックされ、組織のセキュリティ センター ポータルにアラートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="4bfb5-150">アラートには、接続のドメイン名、リモート IP アドレス、デバイスの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="4bfb5-151">さらに、iOS デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="4bfb5-152">通知をタップすると、ユーザーが詳細を確認する次の画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4bfb5-153">![安全でない通知として報告されたサイトの画像](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="4bfb5-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="4bfb5-154">データとプライバシー</span><span class="sxs-lookup"><span data-stu-id="4bfb5-154">Data and Privacy</span></span>

<span data-ttu-id="4bfb5-155">収集されたデータとプライバシーの詳細については、「プライバシー情報 [- Microsoft Defender for Endpoint on iOS」を参照してください](ios-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="4bfb5-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

