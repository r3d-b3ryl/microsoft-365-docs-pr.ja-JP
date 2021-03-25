---
title: Microsoft Defender ATP のセキュリティ ベースラインへの準拠を強化する
description: Microsoft Defender ATP のセキュリティ 基準は、最適な保護を提供するために Microsoft Defender ATP セキュリティコントロールを設定します。
keywords: Intune 管理、MDATP、WDATP、Microsoft Defender、高度な脅威保護 ASR、セキュリティ ベースライン
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
ms.openlocfilehash: 74073441ad7be89e0af278ff1e371133251b5ea7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163401"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="770ef-104">Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する</span><span class="sxs-lookup"><span data-stu-id="770ef-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="770ef-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="770ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="770ef-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="770ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="770ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="770ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="770ef-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="770ef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="770ef-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="770ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="770ef-110">セキュリティ 基準は、セキュリティ専門家と Windows システム管理者の専門家の両方からのガイダンスに従ってセキュリティ機能が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="770ef-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="770ef-111">展開すると、Defender for Endpoint セキュリティ ベースラインは、最適な保護を提供するために Defender for Endpoint セキュリティ コントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="770ef-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="770ef-112">構成プロファイルを使用して Intune でセキュリティ基準がどのように割り当てられているかについて理解するには、この [FAQ を参照してください](https://docs.microsoft.com/intune/security-baselines#q--a)。</span><span class="sxs-lookup"><span data-stu-id="770ef-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="770ef-113">セキュリティ 基準へのコンプライアンスを展開して追跡する前に、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="770ef-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="770ef-114">Intune 管理にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="770ef-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="770ef-115">必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="770ef-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines"></a><span data-ttu-id="770ef-116">Microsoft Defender ATP と Windows Intune のセキュリティ ベースラインを比較する</span><span class="sxs-lookup"><span data-stu-id="770ef-116">Compare the Microsoft Defender ATP and the Windows Intune security baselines</span></span>
<span data-ttu-id="770ef-117">Windows Intune のセキュリティ ベースラインには、ブラウザー設定、PowerShell 設定、Microsoft Defender ウイルス対策などの一部のセキュリティ機能の設定など、Windows を実行しているデバイスを安全に構成するために必要な、一連の推奨設定が提供されています。</span><span class="sxs-lookup"><span data-stu-id="770ef-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="770ef-118">これに対し、Defender for Endpoint ベースラインには、エンドポイント検出と応答 (EDR) の設定、Windows Intune のセキュリティ ベースラインにある設定など、Defender for Endpoint スタック内のすべてのセキュリティ コントロールを最適化する設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="770ef-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="770ef-119">各ベースラインの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="770ef-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="770ef-120">Intune の Windows セキュリティ基準の設定</span><span class="sxs-lookup"><span data-stu-id="770ef-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="770ef-121">Intune の Microsoft Defender ATP ベースライン設定</span><span class="sxs-lookup"><span data-stu-id="770ef-121">Microsoft Defender ATP baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="770ef-122">理想的には、Defender for Endpoint にオンボードされているデバイスは、Windows を最初にセキュリティ保護するための Windows Intune セキュリティ ベースラインと、Defender for Endpoint セキュリティ 基準を上に重ね、Defender for Endpoint セキュリティコントロールを最適に構成するための両方のベースラインを展開します。</span><span class="sxs-lookup"><span data-stu-id="770ef-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="770ef-123">リスクと脅威に関する最新のデータを利用し、ベースラインの進化に伴う競合を最小限に抑えるために、リリース後すぐにすべての製品に最新バージョンのベースラインを適用してください。</span><span class="sxs-lookup"><span data-stu-id="770ef-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="770ef-124">Defender for Endpoint セキュリティ ベースラインは物理デバイス用に最適化されています。現在、仮想マシン (VM) または VDI エンドポイントでの使用は推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="770ef-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="770ef-125">一部の基準設定は、仮想化環境でのリモート 対話型セッションに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770ef-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="770ef-126">Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="770ef-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="770ef-127">デバイス **構成管理の** セキュリティ [基準](configure-machines.md) カードは、Defender for Endpoint セキュリティ ベースラインが割り当てられている Windows 10 デバイス全体のコンプライアンスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="770ef-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="770ef-128">![セキュリティ ベースライン カード](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="770ef-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="770ef-129">*Defender for Endpoint セキュリティ ベースラインへの準拠を示すカード*</span><span class="sxs-lookup"><span data-stu-id="770ef-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="770ef-130">各デバイスには、次のいずれかの状態の種類が与えられます。</span><span class="sxs-lookup"><span data-stu-id="770ef-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="770ef-131">**基準と一致** する —デバイスの設定は、基準計画のすべての設定と一致します</span><span class="sxs-lookup"><span data-stu-id="770ef-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="770ef-132">**ベースラインと一致しない**—少なくとも 1 つのデバイス設定がベースラインと一致しない</span><span class="sxs-lookup"><span data-stu-id="770ef-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="770ef-133">**正しく構成されていない**—少なくとも 1 つの基準設定がデバイスで適切に構成されていない状態で、競合、エラー、または保留中の状態にある</span><span class="sxs-lookup"><span data-stu-id="770ef-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="770ef-134">**適用なし**:少なくとも 1 つの基準計画設定がデバイスに適用されない</span><span class="sxs-lookup"><span data-stu-id="770ef-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="770ef-135">特定のデバイスを確認するには、カード **の [セキュリティ 基準計画の構成** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="770ef-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="770ef-136">これにより、Intune デバイス管理にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="770ef-136">This takes you to Intune device management.</span></span> <span data-ttu-id="770ef-137">そこから、[デバイスの **状態]** を選択して、デバイスの名前と状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="770ef-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="770ef-138">デバイス構成管理ページに表示される集計データと、Intune の概要画面に表示されるデータに不一致が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770ef-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="770ef-139">Microsoft Defender for Endpoint セキュリティ ベースラインの確認と割り当て</span><span class="sxs-lookup"><span data-stu-id="770ef-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="770ef-140">デバイス構成管理は、Microsoft Defender for Endpoint セキュリティ ベースラインが特別に割り当てられている Windows 10 デバイスの基準準拠のみを監視します。</span><span class="sxs-lookup"><span data-stu-id="770ef-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="770ef-141">ベースラインを簡単に確認し、Intune デバイス管理のデバイスに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="770ef-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="770ef-142">[ **セキュリティ ベースライン カードのセキュリティ** 基準を構成する] **を選択** して、Intune デバイス管理に移動します。</span><span class="sxs-lookup"><span data-stu-id="770ef-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="770ef-143">ベースラインコンプライアンスの同様の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="770ef-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="770ef-144">または、Microsoft Defender ATP ベースラインのすべてのサービス > Intune > デバイス セキュリティ > セキュリティ ベースライン> Microsoft Azure ポータルの Defender for Endpoint セキュリティ ベースライン **に移動することもできます**。</span><span class="sxs-lookup"><span data-stu-id="770ef-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="770ef-145">新しいプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="770ef-145">Create a new profile.</span></span>

   <span data-ttu-id="770ef-146">![Intune の Microsoft Defender for Endpoint セキュリティ ベースラインの概要](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="770ef-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="770ef-147">*Intune の Microsoft Defender for Endpoint セキュリティ ベースラインの概要*</span><span class="sxs-lookup"><span data-stu-id="770ef-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="770ef-148">プロファイルの作成中に、基準計画の特定の設定を確認および調整できます。</span><span class="sxs-lookup"><span data-stu-id="770ef-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="770ef-149">![Intune でのプロファイル作成時のセキュリティ基準オプション](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="770ef-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="770ef-150">*Intune でのプロファイル作成時のセキュリティ基準オプション*</span><span class="sxs-lookup"><span data-stu-id="770ef-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="770ef-151">プロファイルを適切なデバイス グループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="770ef-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="770ef-152">![Intune のセキュリティ ベースライン プロファイル](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="770ef-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="770ef-153">*Intune でのセキュリティ 基準プロファイルの割り当て*</span><span class="sxs-lookup"><span data-stu-id="770ef-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="770ef-154">プロファイルを作成して保存し、割り当てられたデバイス グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="770ef-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="770ef-155">![Intune でのセキュリティ 基準の割り当て](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="770ef-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="770ef-156">*Intune でのセキュリティ ベースライン プロファイルの作成*</span><span class="sxs-lookup"><span data-stu-id="770ef-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="770ef-157">Intune のセキュリティ ベースラインは、デバイスを包括的に保護して保護するための便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="770ef-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="770ef-158">[Intune のセキュリティ基準について詳しくは、次のページをご覧ください](https://docs.microsoft.com/intune/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="770ef-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="770ef-159">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="770ef-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="770ef-160">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="770ef-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="770ef-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="770ef-161">Related topics</span></span>
- [<span data-ttu-id="770ef-162">デバイスが正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="770ef-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="770ef-163">Microsoft Defender for Endpoint にオンボードされているデバイスを取得する</span><span class="sxs-lookup"><span data-stu-id="770ef-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="770ef-164">ASR ルールの展開と検出を最適化する</span><span class="sxs-lookup"><span data-stu-id="770ef-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
