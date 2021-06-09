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
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842256"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="28c73-104">iOS の機能で Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="28c73-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28c73-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="28c73-105">**Applies to:**</span></span>
- [<span data-ttu-id="28c73-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28c73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28c73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28c73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28c73-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="28c73-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28c73-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="28c73-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="28c73-110">iOS 上のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="28c73-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="28c73-111">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="28c73-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="28c73-112">iOS 上のエンドポイント用 Defender を使用した条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="28c73-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="28c73-113">Microsoft Defender for Endpoint on iOS および Microsoft Intune および Azure Active Directory を使用すると、デバイス のリスク スコアに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="28c73-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="28c73-114">Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="28c73-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="28c73-115">iOS 上の Defender for Endpoint で条件付きアクセスを設定する方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="28c73-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="28c73-116">Microsoft Defender for Endpoint による脱獄の検出</span><span class="sxs-lookup"><span data-stu-id="28c73-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="28c73-117">Microsoft Defender for Endpoint には、脱獄された管理されていないデバイスと管理対象デバイスを検出する機能があります。</span><span class="sxs-lookup"><span data-stu-id="28c73-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="28c73-118">デバイスが脱獄されたと検出された場合、危険度の高いアラートがセキュリティ センターに報告され、条件付きアクセスがデバイス リスク スコアに基づいてセットアップされている場合、デバイスは企業データへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="28c73-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="28c73-119">Web 保護と VPN</span><span class="sxs-lookup"><span data-stu-id="28c73-119">Web Protection and VPN</span></span>

<span data-ttu-id="28c73-120">既定では、Defender for Endpoint on iOS には Web 保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="28c73-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="28c73-121">[Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28c73-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="28c73-122">iOS のエンドポイントの Defender は、この保護を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="28c73-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="28c73-123">これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。</span><span class="sxs-lookup"><span data-stu-id="28c73-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="28c73-124">既定で有効になっている場合は、VPN を無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="28c73-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="28c73-125">たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。</span><span class="sxs-lookup"><span data-stu-id="28c73-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="28c73-126">このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="28c73-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="28c73-127">iOS デバイスで、アプリを開き **設定[全般**] をクリック **またはタップ** し **、[VPN] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="28c73-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="28c73-128">Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="28c73-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="28c73-129">VPN を無効 **にするにはConnectをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="28c73-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="28c73-130">![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="28c73-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="28c73-131">VPN が無効になっている場合、Web 保護は使用できません。</span><span class="sxs-lookup"><span data-stu-id="28c73-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="28c73-132">Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。</span><span class="sxs-lookup"><span data-stu-id="28c73-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="28c73-133">複数の VPN プロファイルの共存在</span><span class="sxs-lookup"><span data-stu-id="28c73-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="28c73-134">Apple iOS では、同時にアクティブになる複数のデバイス全体の VPN はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="28c73-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="28c73-135">デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="28c73-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="28c73-136">脱獄されたデバイスに対するコンプライアンス ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="28c73-136">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="28c73-137">企業データが脱獄された iOS デバイスでアクセスされるのを保護するには、Intune で次のコンプライアンス ポリシーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28c73-137">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="28c73-138">脱獄検出は、iOS 上の Microsoft Defender for Endpoint によって提供される機能です。</span><span class="sxs-lookup"><span data-stu-id="28c73-138">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="28c73-139">ただし、脱獄シナリオに対する追加の防御層としてこのポリシーをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28c73-139">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="28c73-140">以下の手順に従って、脱獄されたデバイスに対するコンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="28c73-140">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="28c73-141">管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス コンプライアンス ポリシー  ->  **の作成ポリシー**]  ->  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="28c73-141">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="28c73-142">プラットフォームとして [iOS/iPadOS] を選択し、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="28c73-142">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="28c73-143">![ポリシーの作成](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="28c73-143">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="28c73-144">ポリシーの名前を指定します 。たとえば、「脱獄のコンプライアンス ポリシー」などです。</span><span class="sxs-lookup"><span data-stu-id="28c73-144">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="28c73-145">[コンプライアンス設定] ページで、[デバイスの正常性] セクションをクリック **し、[脱** 獄デバイスのブロック **] フィールドをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="28c73-145">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="28c73-146">![ポリシー設定](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="28c73-146">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="28c73-147">[非 *準拠のアクション] セクションで* 、要件に従ってアクションを選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="28c73-147">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="28c73-148">![ポリシーアクション](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="28c73-148">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="28c73-149">[割 *り当て* ] セクションで、このポリシーに含めるユーザー グループを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="28c73-149">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="28c73-150">[レビュー **+ 作成] セクション** で、入力した情報が正しいか確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="28c73-150">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="28c73-151">カスタム インジケーターの構成</span><span class="sxs-lookup"><span data-stu-id="28c73-151">Configure custom indicators</span></span>

<span data-ttu-id="28c73-152">iOS のエンドポイントの Defender を使用すると、管理者は iOS デバイス上のカスタム インジケーターも構成できます。</span><span class="sxs-lookup"><span data-stu-id="28c73-152">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="28c73-153">カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="28c73-153">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="28c73-154">IOS のエンドポイントの Defender は、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="28c73-154">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="28c73-155">安全でないサイトを報告する</span><span class="sxs-lookup"><span data-stu-id="28c73-155">Report unsafe site</span></span>

<span data-ttu-id="28c73-156">フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。</span><span class="sxs-lookup"><span data-stu-id="28c73-156">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="28c73-157">フィッシング サイト [の可能性がある Web サイトを報告](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) する場合は、[ネットワーク保護に関するフィードバックを提供する] ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="28c73-157">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

