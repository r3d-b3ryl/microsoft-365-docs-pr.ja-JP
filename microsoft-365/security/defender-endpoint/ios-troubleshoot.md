---
title: iOS 上の Microsoft Defender for Endpoint に関連する FAQ に関する問題のトラブルシューティングと回答の検索
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
ms.openlocfilehash: 2f9d56b7e72befb8acddf6d9f810a7ba5cec1083
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694367"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="782d3-104">iOS 上の Microsoft Defender for Endpoint で問題のトラブルシューティングを行い、FAQ に対する回答を見つける</span><span class="sxs-lookup"><span data-stu-id="782d3-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="782d3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="782d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="782d3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="782d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="782d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="782d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="782d3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="782d3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="782d3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="782d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="782d3-110">このトピックでは、iOS で Microsoft Defender for Endpoint を使用する際に発生する可能性のある問題に対処するためのトラブルシューティング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="782d3-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="782d3-111">iOS 上のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="782d3-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="782d3-112">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="782d3-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="782d3-113">VPN が有効になっているとアプリが動作しない</span><span class="sxs-lookup"><span data-stu-id="782d3-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="782d3-114">アクティブな VPN が検出されると、機能を停止するアプリがあります。</span><span class="sxs-lookup"><span data-stu-id="782d3-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="782d3-115">このようなアプリを使用している間は、VPN を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="782d3-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="782d3-116">既定では、Defender for Endpoint on iOS には Web 保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="782d3-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="782d3-117">[Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="782d3-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="782d3-118">iOS のエンドポイントの Defender は、この保護を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="782d3-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="782d3-119">これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="782d3-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="782d3-120">既定で有効になっている場合は、VPN を無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="782d3-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="782d3-121">たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。</span><span class="sxs-lookup"><span data-stu-id="782d3-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="782d3-122">このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="782d3-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="782d3-123">iOS デバイスで、アプリを開き **設定[全般**] をクリック **またはタップ** し **、[VPN] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="782d3-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="782d3-124">Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="782d3-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="782d3-125">VPN を無効 **にするにはConnectをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="782d3-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="782d3-126">![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="782d3-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="782d3-127">VPN が無効になっている場合、Web 保護は使用できません。</span><span class="sxs-lookup"><span data-stu-id="782d3-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="782d3-128">Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。</span><span class="sxs-lookup"><span data-stu-id="782d3-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="782d3-129">複数の VPN プロファイルに関する問題</span><span class="sxs-lookup"><span data-stu-id="782d3-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="782d3-130">Apple iOS では、同時にアクティブになる複数のデバイス全体の **VPN** はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="782d3-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="782d3-131">デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="782d3-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="782d3-132">Microsoft Defender for Endpoint VPN は、アプリ単位または "個人用" として構成されている他の VPN と *共に存在できます*。</span><span class="sxs-lookup"><span data-stu-id="782d3-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="782d3-133">バッテリー消費</span><span class="sxs-lookup"><span data-stu-id="782d3-133">Battery consumption</span></span>

<span data-ttu-id="782d3-134">アプリでは設定 iOS は、特定の期間、ユーザーに表示されるアプリのバッテリー使用量のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="782d3-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="782d3-135">画面に表示されるアプリのバッテリー使用量は、その期間のみであり、CPU やネットワークの使用状況などの多数の要因に基づいて iOS によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="782d3-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="782d3-136">Microsoft Defender for Endpoint では、バックグラウンドでローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="782d3-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="782d3-137">任意のアプリからのネットワーク パケットは、このチェックを通過し、Microsoft Defender for Endpoint のバッテリー使用量が不正確に計算される原因になります。</span><span class="sxs-lookup"><span data-stu-id="782d3-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="782d3-138">Microsoft Defender for Endpoint の実際のバッテリー消費量は、デバイスの [バッテリー] ページに表示される設定はるかに少ない値です。</span><span class="sxs-lookup"><span data-stu-id="782d3-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="782d3-139">バックグラウンドで実行されている Microsoft Defender for Endpoint による 1 日あたりの平均バッテリー使用量は、その日に消費されたバッテリー全体の約 **8.81% です**。</span><span class="sxs-lookup"><span data-stu-id="782d3-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="782d3-140">この指標は、エンド ユーザー デバイスでの Microsoft Defender for Endpoint の実際の使用状況に基づいて Apple によって報告され、上記の理由により、ネットワーク アクティビティを持つ他のアプリも考慮できます。</span><span class="sxs-lookup"><span data-stu-id="782d3-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="782d3-141">また、使用される VPN はローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="782d3-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="782d3-142">データの使用状況</span><span class="sxs-lookup"><span data-stu-id="782d3-142">Data usage</span></span>

<span data-ttu-id="782d3-143">Microsoft Defender for Endpoint では、ローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="782d3-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="782d3-144">このため、Microsoft Defender for Endpoint データの使用状況が不正確に説明される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="782d3-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="782d3-145">Microsoft Defender for Endpoint による実際のデータ使用量は、デバイス上の [データ使用状況] ページに表示されるデータ使用量よりも設定小さい値です。</span><span class="sxs-lookup"><span data-stu-id="782d3-145">The actual data usage by Microsoft Defender for Endpoint is not significant and lesser than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="782d3-146">安全でないサイトを報告する</span><span class="sxs-lookup"><span data-stu-id="782d3-146">Report unsafe site</span></span>

<span data-ttu-id="782d3-147">フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。</span><span class="sxs-lookup"><span data-stu-id="782d3-147">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="782d3-148">[ネットワーク [保護に関するフィードバックを提供する](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) ] ページにアクセスして、フィッシング サイトになる可能性のある Web サイトを報告します。</span><span class="sxs-lookup"><span data-stu-id="782d3-148">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="782d3-149">悪意のあるサイトが検出されました</span><span class="sxs-lookup"><span data-stu-id="782d3-149">Malicious site detected</span></span>

<span data-ttu-id="782d3-150">Microsoft Defender for Endpoint は、フィッシングなどの Web ベースの攻撃からユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="782d3-150">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="782d3-151">悪意のあるサイトが検出されると、接続がブロックされ、組織のセキュリティ センター ポータルにアラートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="782d3-151">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="782d3-152">アラートには、接続のドメイン名、リモート IP アドレス、デバイスの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="782d3-152">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="782d3-153">さらに、iOS デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="782d3-153">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="782d3-154">通知をタップすると、ユーザーが詳細を確認する次の画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="782d3-154">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="782d3-155">![安全でない通知として報告されたサイトの画像](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="782d3-155">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="782d3-156">データとプライバシー</span><span class="sxs-lookup"><span data-stu-id="782d3-156">Data and Privacy</span></span>

<span data-ttu-id="782d3-157">収集されたデータとプライバシーの詳細については、「プライバシー情報 [- Microsoft Defender for Endpoint on iOS」を参照してください](ios-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="782d3-157">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

