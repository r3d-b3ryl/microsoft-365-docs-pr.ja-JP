---
title: デバイスが正しく構成されていることを確認する
description: デバイスを適切に構成して、脅威に対する全体的な回復力を高め、攻撃を検出して対応する機能を強化します。
keywords: オンボード、Intune 管理、Microsoft Defender for Endpoint、Microsoft Defender、Windows Defender、攻撃表面の縮小、ASR、セキュリティ ベースライン
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3fd58ee17b2cb86c0bcc858b9b0fd57c12ac501e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932813"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="82b99-104">デバイスが正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="82b99-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82b99-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="82b99-105">**Applies to:**</span></span>
- [<span data-ttu-id="82b99-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="82b99-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82b99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82b99-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="82b99-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="82b99-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82b99-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="82b99-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="82b99-110">適切に構成されたデバイスを使用すると、脅威に対する全体的な回復力を高め、攻撃を検出して対応する機能を強化できます。</span><span class="sxs-lookup"><span data-stu-id="82b99-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="82b99-111">セキュリティ構成管理は、デバイスが次の条件を確実に実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82b99-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="82b99-112">エンドポイント用 Microsoft Defender にオンボード</span><span class="sxs-lookup"><span data-stu-id="82b99-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="82b99-113">Defender for Endpoint セキュリティ ベースライン構成を満たすか超過する</span><span class="sxs-lookup"><span data-stu-id="82b99-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="82b99-114">戦略的な攻撃表面の軽減策を設定する</span><span class="sxs-lookup"><span data-stu-id="82b99-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="82b99-115">ナビゲーション **メニューから [構成の** 管理] をクリックして、[デバイス構成管理] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="82b99-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="82b99-116">![[セキュリティ構成管理] ページ](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="82b99-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="82b99-117">*デバイス構成管理ページ*</span><span class="sxs-lookup"><span data-stu-id="82b99-117">*Device configuration management page*</span></span>

<span data-ttu-id="82b99-118">Microsoft Intune および Microsoft 365 セキュリティ センターのデバイス管理ページへの直接の詳細なリンクを通じて、組織レベルで構成状態を追跡し、オンボーディングのカバレッジの低下、コンプライアンスの問題、および最適化の不十分な攻撃表面の軽減策に対応して迅速にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82b99-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="82b99-119">そうすることで、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="82b99-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="82b99-120">デバイス上のイベントの包括的な可視性</span><span class="sxs-lookup"><span data-stu-id="82b99-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="82b99-121">堅牢な脅威インテリジェンスと、生のイベントを処理し、侵害アクティビティと脅威インジケーターを特定するための強力なデバイス学習テクノロジ</span><span class="sxs-lookup"><span data-stu-id="82b99-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="82b99-122">悪意のあるインプラントのインストールを効率的に停止するように構成されたセキュリティ機能の完全なスタック、システム ファイルとプロセスのハイジャック、データの侵入、その他の脅威アクティビティ</span><span class="sxs-lookup"><span data-stu-id="82b99-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="82b99-123">最適化された攻撃表面の軽減、脅威アクティビティに対する戦略的防御を最大化し、生産性への影響を最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="82b99-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="82b99-124">Intune 管理へのデバイスの登録</span><span class="sxs-lookup"><span data-stu-id="82b99-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="82b99-125">デバイス構成管理は、Intune デバイス管理と密接に関係して、組織内のデバイスのインベントリとベースライン セキュリティ構成を確立します。</span><span class="sxs-lookup"><span data-stu-id="82b99-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="82b99-126">Intune で管理されている Windows 10 デバイスで構成の問題を追跡および管理できます。</span><span class="sxs-lookup"><span data-stu-id="82b99-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="82b99-127">デバイスが適切に構成されていることを確認する前に、デバイスを Intune 管理に登録します。</span><span class="sxs-lookup"><span data-stu-id="82b99-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="82b99-128">Intune の登録は堅牢で、Windows 10 デバイスのいくつかの登録オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="82b99-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="82b99-129">Intune 登録オプションの詳細については、「Windows デバイスの登録 [の設定」を参照してください](https://docs.microsoft.com/intune/windows-enroll)。</span><span class="sxs-lookup"><span data-stu-id="82b99-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="82b99-130">Windows デバイスを Intune に登録するには、管理者に既にライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b99-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="82b99-131">[デバイス登録のライセンスの割り当てに関する記事をご覧ください](https://docs.microsoft.com/intune/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="82b99-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="82b99-132">Intune を使用してデバイス管理を最適化するには [、Intune を Defender for Endpoint に接続します](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="82b99-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="82b99-133">必要なアクセス許可を取得する</span><span class="sxs-lookup"><span data-stu-id="82b99-133">Obtain required permissions</span></span>
<span data-ttu-id="82b99-134">既定では、Azure AD のグローバル管理者または Intune Service Administrator ロールが割り当てられているユーザーだけが、デバイスのオンボーディングとセキュリティ ベースラインの展開に必要なデバイス構成プロファイルを管理および割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="82b99-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="82b99-135">他の役割が割り当てられている場合は、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b99-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="82b99-136">デバイス構成に対する完全なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="82b99-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="82b99-137">セキュリティ 基準に対する完全なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="82b99-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="82b99-138">デバイス コンプライアンス ポリシーへの読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="82b99-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="82b99-139">組織へのアクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="82b99-139">Read permissions to the organization</span></span>

<span data-ttu-id="82b99-140">![Intune で必要なアクセス許可](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="82b99-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="82b99-141">*Intune のデバイス構成のアクセス許可*</span><span class="sxs-lookup"><span data-stu-id="82b99-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="82b99-142">Intune にアクセス許可を割り当てる方法の詳細については、「カスタム [ロールの作成」を参照してください](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)。</span><span class="sxs-lookup"><span data-stu-id="82b99-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="82b99-143">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="82b99-143">In this section</span></span>
<span data-ttu-id="82b99-144">トピック</span><span class="sxs-lookup"><span data-stu-id="82b99-144">Topic</span></span> | <span data-ttu-id="82b99-145">説明</span><span class="sxs-lookup"><span data-stu-id="82b99-145">Description</span></span>
:---|:---
[<span data-ttu-id="82b99-146">Defender for Endpoint にオンボードされているデバイスを取得する</span><span class="sxs-lookup"><span data-stu-id="82b99-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="82b99-147">Intune で管理されているデバイスのオンボーディング状態を追跡し、Intune を介してその他のデバイスをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="82b99-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="82b99-148">Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する</span><span class="sxs-lookup"><span data-stu-id="82b99-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="82b99-149">ベースラインのコンプライアンスと非準拠を追跡します。</span><span class="sxs-lookup"><span data-stu-id="82b99-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="82b99-150">セキュリティ ベースラインを Intune で管理されるその他のデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="82b99-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="82b99-151">ASR ルールの展開と検出を最適化する</span><span class="sxs-lookup"><span data-stu-id="82b99-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="82b99-152">Microsoft 365 セキュリティ センターの影響分析ツールを使用して、ルールの展開を確認し、検出を調整します。</span><span class="sxs-lookup"><span data-stu-id="82b99-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="82b99-153">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="82b99-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82b99-154">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="82b99-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
