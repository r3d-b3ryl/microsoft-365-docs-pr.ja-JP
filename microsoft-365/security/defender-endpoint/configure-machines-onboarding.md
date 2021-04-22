---
title: Microsoft Defender for Endpoint にオンボードされているデバイスを取得する
description: Intune で管理されたデバイスの Microsoft Defender for Endpoint へのオンボーディングを追跡し、オンボーディング 速度を向上します。
keywords: オンボード、Intune 管理、Microsoft Defender for Endpoint、Microsoft Defender、Windows Defender、構成管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e0d5a13b0c33516209bd2d18361a1de6ab9245c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932943"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="28d97-104">Microsoft Defender for Endpoint にオンボードされているデバイスを取得する</span><span class="sxs-lookup"><span data-stu-id="28d97-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28d97-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="28d97-105">**Applies to:**</span></span>
- [<span data-ttu-id="28d97-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28d97-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28d97-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28d97-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="28d97-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="28d97-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28d97-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="28d97-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="28d97-110">オンボードされた各デバイスは、追加のエンドポイント検出と応答 (EDR) センサーを追加し、ネットワーク内の侵害アクティビティに対する可視性を向上します。</span><span class="sxs-lookup"><span data-stu-id="28d97-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="28d97-111">また、オンボーディングにより、デバイスで脆弱なコンポーネントやセキュリティ構成の問題をチェックし、攻撃中に重大な修復アクションを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28d97-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="28d97-112">デバイスのオンボーディングを追跡および管理する前に、</span><span class="sxs-lookup"><span data-stu-id="28d97-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="28d97-113">Intune 管理にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="28d97-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="28d97-114">必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="28d97-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="28d97-115">保護されていないデバイスの検出と追跡</span><span class="sxs-lookup"><span data-stu-id="28d97-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="28d97-116">**オンボーディング** カードは、実際に Defender for Endpoint にオンボードされた Windows 10 デバイスの数と Intune で管理される Windows 10 デバイスの総数を比較することで、オンボーディング レートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="28d97-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="28d97-117">![デバイス構成管理オンボード カード](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="28d97-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="28d97-118">*Intune で管理されている Windows 10 デバイスの総数と比較したオンボード デバイスを示すカード*</span><span class="sxs-lookup"><span data-stu-id="28d97-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="28d97-119">セキュリティ センター構成マネージャー、オンボーディング スクリプト、または Intune プロファイルを使用しないその他のオンボーディング 方法を使用した場合、データの不一致が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28d97-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="28d97-120">これらの不一致を解決するには、Defender for Endpoint オンボーディングに対応する Intune 構成プロファイルを作成し、そのプロファイルをデバイスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="28d97-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="28d97-121">Intune プロファイルを使用して他のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="28d97-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="28d97-122">Defender for Endpoint は [、Windows 10 デバイスのオンボードに便利ないくつかのオプションを提供します](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="28d97-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="28d97-123">ただし、Intune で管理されるデバイスの場合は、Intune プロファイルを活用して Defender for Endpoint センサーを便利に展開してデバイスを選択し、これらのデバイスをサービスに効果的にオンボーディングできます。</span><span class="sxs-lookup"><span data-stu-id="28d97-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="28d97-124">[オンボード] **カードで、[** その他のデバイス **の** オンボード] を選択して、Intune でプロファイルを作成して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="28d97-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="28d97-125">このリンクを使用すると、Intune のデバイス コンプライアンス ページに移動し、オンボーディング状態の同様の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="28d97-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="28d97-126">![Intune デバイス管理の Microsoft Defender for Endpoint デバイスコンプライアンス ページ](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="28d97-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="28d97-127">*Intune デバイス管理の Microsoft Defender for Endpoint デバイスコンプライアンス ページ*</span><span class="sxs-lookup"><span data-stu-id="28d97-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="28d97-128">または、Microsoft Defender ATP のすべてのサービス > Intune > デバイス コンプライアンス> Microsoft [Azure](https://portal.azure.com/) ポータルの [Defender for Endpoint オンボーディング コンプライアンス] **ページに** 移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="28d97-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="28d97-129">最新のデバイス データを表示する場合は、[ATP センサーのないデバイスの一覧 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="28d97-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="28d97-130">[デバイスコンプライアンス] ページで、Defender for Endpoint センサーの展開専用の構成プロファイルを作成し、そのプロファイルをオンボードするデバイスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="28d97-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="28d97-131">これを行うには、次のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="28d97-131">To do this, you can either:</span></span>

- <span data-ttu-id="28d97-132">[ **デバイス構成プロファイルの作成] を選択して、定義済** みのデバイス構成プロファイルから開始する ATP センサーを構成します。</span><span class="sxs-lookup"><span data-stu-id="28d97-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="28d97-133">デバイス構成プロファイルを最初から作成します。</span><span class="sxs-lookup"><span data-stu-id="28d97-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="28d97-134">詳細については [、「Intune デバイス構成プロファイルを使用してデバイスを Defender for Endpoint にオンボードする」を参照してください](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="28d97-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="28d97-135">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="28d97-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28d97-136">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="28d97-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="28d97-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="28d97-137">Related topics</span></span>
- [<span data-ttu-id="28d97-138">デバイスが正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="28d97-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="28d97-139">Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する</span><span class="sxs-lookup"><span data-stu-id="28d97-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="28d97-140">ASR ルールの展開と検出を最適化する</span><span class="sxs-lookup"><span data-stu-id="28d97-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
