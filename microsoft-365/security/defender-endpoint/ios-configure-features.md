---
title: iOS の機能で Microsoft Defender for Endpoint を構成する
description: iOS 機能に Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245278"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="6670e-104">iOS の機能で Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="6670e-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6670e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6670e-105">**Applies to:**</span></span>
- [<span data-ttu-id="6670e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6670e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6670e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6670e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6670e-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6670e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6670e-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="6670e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="6670e-110">iOS 上のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6670e-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="6670e-111">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="6670e-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="6670e-112">iOS 上のエンドポイント用 Defender を使用した条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="6670e-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="6670e-113">Microsoft Defender for Endpoint on iOS および Microsoft Intune および Azure Active Directory を使用すると、デバイス のリスク スコアに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="6670e-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="6670e-114">Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="6670e-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="6670e-115">iOS 上の Defender for Endpoint で条件付きアクセスを設定する方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="6670e-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="6670e-116">**iOS 上の Microsoft Defender for Endpoint による脱獄検出は現在プレビュー中です**。</span><span class="sxs-lookup"><span data-stu-id="6670e-116">**Jailbreak detection by Microsoft Defender for Endpoint on iOS is currently in preview**.</span></span> <span data-ttu-id="6670e-117">Microsoft Defender for Endpoint によってデバイスが脱獄されたと検出された場合、高リスクアラートがセキュリティ センターに報告され、条件付きアクセスがデバイス リスク スコアに基づいてセットアップされている場合、デバイスは企業データへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6670e-117">If a device is detected to be jailbroken by Microsoft Defender for Endpoint, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="6670e-118">Web 保護と VPN</span><span class="sxs-lookup"><span data-stu-id="6670e-118">Web Protection and VPN</span></span>

<span data-ttu-id="6670e-119">既定では、Defender for Endpoint on iOS には Web 保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6670e-119">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="6670e-120">[Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6670e-120">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="6670e-121">iOS のエンドポイントの Defender は、この保護を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6670e-121">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="6670e-122">これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="6670e-122">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="6670e-123">既定で有効になっている場合は、VPN を無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6670e-123">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="6670e-124">たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。</span><span class="sxs-lookup"><span data-stu-id="6670e-124">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="6670e-125">このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="6670e-125">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="6670e-126">iOS デバイスで、アプリを開き **設定[全般**] をクリック **またはタップ** し **、[VPN] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="6670e-126">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="6670e-127">Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="6670e-127">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="6670e-128">VPN を無効 **にするにはConnectをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="6670e-128">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6670e-129">![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="6670e-129">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="6670e-130">VPN が無効になっている場合、Web 保護は使用できません。</span><span class="sxs-lookup"><span data-stu-id="6670e-130">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="6670e-131">Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。</span><span class="sxs-lookup"><span data-stu-id="6670e-131">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="6670e-132">複数の VPN プロファイルの共存在</span><span class="sxs-lookup"><span data-stu-id="6670e-132">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="6670e-133">Apple iOS では、同時にアクティブになる複数のデバイス全体の VPN はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6670e-133">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="6670e-134">デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="6670e-134">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="6670e-135">脱獄されたデバイスに対するコンプライアンス ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6670e-135">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="6670e-136">企業データが脱獄された iOS デバイスでアクセスされるのを保護するには、Intune で次のコンプライアンス ポリシーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6670e-136">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="6670e-137">現時点では、iOS 上の Microsoft Defender for Endpoint による脱獄検出はプレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="6670e-137">At this time jailbreak detection by Microsoft Defender for Endpoint on iOS is in preview.</span></span> <span data-ttu-id="6670e-138">脱獄シナリオに対する追加の防御層としてこのポリシーをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6670e-138">We recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="6670e-139">以下の手順に従って、脱獄されたデバイスに対するコンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6670e-139">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="6670e-140">管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス コンプライアンス ポリシー  ->  **の作成ポリシー**]  ->  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6670e-140">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="6670e-141">プラットフォームとして [iOS/iPadOS] を選択し、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6670e-141">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6670e-142">![ポリシーの作成](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="6670e-142">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="6670e-143">ポリシーの名前を指定します 。たとえば、「脱獄のコンプライアンス ポリシー」などです。</span><span class="sxs-lookup"><span data-stu-id="6670e-143">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="6670e-144">[コンプライアンス設定] ページで、[デバイスの正常性] セクションをクリック **し、[脱** 獄デバイスのブロック **] フィールドをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="6670e-144">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6670e-145">![ポリシー設定](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="6670e-145">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="6670e-146">[非 *準拠のアクション] セクションで* 、要件に従ってアクションを選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6670e-146">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6670e-147">![ポリシーアクション](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="6670e-147">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="6670e-148">[割 *り当て* ] セクションで、このポリシーに含めるユーザー グループを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6670e-148">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="6670e-149">[レビュー **+ 作成] セクション** で、入力した情報が正しいか確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6670e-149">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="6670e-150">カスタム インジケーターの構成</span><span class="sxs-lookup"><span data-stu-id="6670e-150">Configure custom indicators</span></span>

<span data-ttu-id="6670e-151">iOS のエンドポイントの Defender を使用すると、管理者は iOS デバイス上のカスタム インジケーターも構成できます。</span><span class="sxs-lookup"><span data-stu-id="6670e-151">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="6670e-152">カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="6670e-152">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="6670e-153">IOS のエンドポイントの Defender は、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6670e-153">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="6670e-154">安全でないサイトを報告する</span><span class="sxs-lookup"><span data-stu-id="6670e-154">Report unsafe site</span></span>

<span data-ttu-id="6670e-155">フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。</span><span class="sxs-lookup"><span data-stu-id="6670e-155">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="6670e-156">フィッシング サイト [の可能性がある Web サイトを報告](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) する場合は、[ネットワーク保護に関するフィードバックを提供する] ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6670e-156">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="6670e-157">Microsoft Defender for Endpoint がインストールされている場合の iOS でのバッテリー消費の問題</span><span class="sxs-lookup"><span data-stu-id="6670e-157">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="6670e-158">アプリによるバッテリー使用量は、CPU やネットワークの使用状況など、さまざまな要因に基づいて Apple によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="6670e-158">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="6670e-159">Microsoft Defender for Endpoint では、バックグラウンドでローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="6670e-159">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6670e-160">任意のアプリからのネットワーク パケットは、このチェックを通過し、Microsoft Defender for Endpoint のバッテリー使用量が不正確に計算される原因になります。</span><span class="sxs-lookup"><span data-stu-id="6670e-160">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="6670e-161">これは、ユーザーに誤った印象を与えます。</span><span class="sxs-lookup"><span data-stu-id="6670e-161">This gives a false impression to the user.</span></span> <span data-ttu-id="6670e-162">Microsoft Defender for Endpoint の実際のバッテリー消費量は、デバイスの [バッテリー] ページに表示設定より小さいです。</span><span class="sxs-lookup"><span data-stu-id="6670e-162">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="6670e-163">これは、バッテリー消費を理解するために Microsoft Defender for Endpoint アプリで実施されたテストに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="6670e-163">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="6670e-164">また、使用される VPN はローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="6670e-164">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
