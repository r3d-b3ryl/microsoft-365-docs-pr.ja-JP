---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントの検出と応答の詳細
keywords: Microsoft Defender for Endpoint, mde, EDRモード, パッシブ モードのブロック
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b0fe1da56c34cd0a79e1a41dba2fcb7a79c5a9f6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259573"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="62a03-104">ブロック モードでのエンドポイントEDR応答 (EDR)</span><span class="sxs-lookup"><span data-stu-id="62a03-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62a03-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="62a03-105">**Applies to:**</span></span>
- [<span data-ttu-id="62a03-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62a03-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62a03-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62a03-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="62a03-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="62a03-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="62a03-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="62a03-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="62a03-110">ブロック モードEDR機能とは</span><span class="sxs-lookup"><span data-stu-id="62a03-110">What is EDR in block mode?</span></span>

<span data-ttu-id="62a03-111">[ブロック モードでのエンドポイント](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)EDR応答 (Microsoft Defender ウイルス対策) は、パッシブ モードで実行されている場合でも、悪意のあるアーティファクトからの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="62a03-111">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="62a03-112">オンにすると、EDRモードでデバイスで検出された悪意のあるアーティファクトや動作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="62a03-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="62a03-113">EDRモードでは、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。</span><span class="sxs-lookup"><span data-stu-id="62a03-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="62a03-114">EDRモードの場合は、脅威の検出[と統合& 脆弱性の管理。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="62a03-114">EDR in block mode is also integrated with [threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="62a03-115">組織のセキュリティ チームは、まだ有効[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)になっていない場合EDRモードで有効にするセキュリティの推奨事項を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="62a03-115">Your organization's security team will get a [security recommendation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードでEDRする推奨事項":::

> [!NOTE]
> <span data-ttu-id="62a03-117">最適な保護を得る場合は、 **[必ず Microsoft Defender for Endpoint ベースラインを展開してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**。</span><span class="sxs-lookup"><span data-stu-id="62a03-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="62a03-118">何かが検出されると何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="62a03-118">What happens when something is detected?</span></span>

<span data-ttu-id="62a03-119">ブロック EDRがオンになっていて、悪意のあるアーティファクトが検出されると、Microsoft Defender for Endpoint は、そのアーティファクトをブロックして修復します。</span><span class="sxs-lookup"><span data-stu-id="62a03-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="62a03-120">アクション センターには、検出の状態が **[ブロック**] または [防止済み] として完了したアクションとして [表示されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)。</span><span class="sxs-lookup"><span data-stu-id="62a03-120">You'll see detection status as **Blocked** or **Prevented** as completed actions in the [Action center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).</span></span>

<span data-ttu-id="62a03-121">次の図は、ブロック モードで検出され、ブロックされたソフトウェアのインスタンスEDR示しています。</span><span class="sxs-lookup"><span data-stu-id="62a03-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDRモードで何かが検出された場合":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="62a03-123">ブロック モードEDR有効にする</span><span class="sxs-lookup"><span data-stu-id="62a03-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62a03-124">ブロック モードで[オンにする前](#requirements-for-edr-in-block-mode)に、要件EDR確認してください。</span><span class="sxs-lookup"><span data-stu-id="62a03-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="62a03-125">[パスワード] ( ) にMicrosoft Defender セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="62a03-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="62a03-126">[高度  >  **設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62a03-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="62a03-127">ブロック モードで **EDRをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="62a03-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="62a03-128">EDRモードの場合は、ブロック モードでのみ有効Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="62a03-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="62a03-129">レジストリ キー、Intune、またはグループ ポリシーを使用して、ブロック モードでEDR無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="62a03-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="62a03-130">ブロック モードでのEDRの要件</span><span class="sxs-lookup"><span data-stu-id="62a03-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="62a03-131">要件</span><span class="sxs-lookup"><span data-stu-id="62a03-131">Requirement</span></span>  |<span data-ttu-id="62a03-132">詳細</span><span class="sxs-lookup"><span data-stu-id="62a03-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="62a03-133">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="62a03-133">Permissions</span></span> |<span data-ttu-id="62a03-134">グローバル管理者またはセキュリティ管理者の役割は、Azure Active Directory で[割り当てられます](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="62a03-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="62a03-135">「基本 [アクセス許可」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。</span><span class="sxs-lookup"><span data-stu-id="62a03-135">See [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions).</span></span> |
|<span data-ttu-id="62a03-136">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="62a03-136">Operating system</span></span>     |<span data-ttu-id="62a03-137">次のいずれかのバージョン。</span><span class="sxs-lookup"><span data-stu-id="62a03-137">One of the following versions:</span></span> <br/><span data-ttu-id="62a03-138">- Windows 10 (すべてのリリース)</span><span class="sxs-lookup"><span data-stu-id="62a03-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="62a03-139">- Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="62a03-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="62a03-140">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="62a03-140">- Windows Server 2019</span></span>  <p><span data-ttu-id="62a03-141">**注**: EDRモードの設定は、ブロック モードではWindows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="62a03-141">**NOTE**: EDR in block mode is not supported on Windows Server 2016.</span></span>       |
|<span data-ttu-id="62a03-142">WindowsE5 登録</span><span class="sxs-lookup"><span data-stu-id="62a03-142">Windows E5 enrollment</span></span>     |<span data-ttu-id="62a03-143">WindowsE5 は、次のサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="62a03-143">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="62a03-144">- Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="62a03-144">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="62a03-145">- Microsoft 365 E3脅威保護サービスと&を組み合わせて使用する</span><span class="sxs-lookup"><span data-stu-id="62a03-145">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="62a03-146">「[各プランの](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)[コンポーネントと機能」を参照してください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="62a03-146">See [Components](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="62a03-147">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="62a03-147">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="62a03-148">Microsoft Defender ウイルス対策アクティブ モードまたはパッシブ モードでインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a03-148">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="62a03-149">(Microsoft 以外のウイルスMicrosoft Defender ウイルス対策と一緒に使用できます。[アクティブMicrosoft Defender ウイルス対策パッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="62a03-149">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="62a03-150">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="62a03-150">Cloud-delivered protection</span></span> |<span data-ttu-id="62a03-151">クラウド配信Microsoft Defender ウイルス対策有効にするように構成[されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="62a03-151">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).</span></span> |
|<span data-ttu-id="62a03-152">Microsoft Defender ウイルス対策マルウェア対策クライアント</span><span class="sxs-lookup"><span data-stu-id="62a03-152">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="62a03-153">クライアントが最新の情報に更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a03-153">Make sure your client is up to date.</span></span> <span data-ttu-id="62a03-154">PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="62a03-154">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="62a03-155">**AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62a03-155">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="62a03-156">Microsoft Defender ウイルス対策 エンジン</span><span class="sxs-lookup"><span data-stu-id="62a03-156">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="62a03-157">エンジンが最新の情報に更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a03-157">Make sure your engine is up to date.</span></span> <span data-ttu-id="62a03-158">PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="62a03-158">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="62a03-159">**AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62a03-159">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="62a03-160">最高の保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外 [が構成されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="62a03-160">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="62a03-161">EDRモードでは、ブロック モードに対して定義されている除外をMicrosoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="62a03-161">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="62a03-162">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="62a03-162">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="62a03-163">デバイスで実行しているEDR場合でも、ブロック モードでMicrosoft Defender ウイルス対策する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="62a03-163">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="62a03-164">パッシブ モードでもEDRモードでも、ブロック モードMicrosoft Defender ウイルス対策状態を維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62a03-164">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="62a03-165">EDRモードでは、Microsoft Defender for Endpoint を使用して別の防御層を提供します。</span><span class="sxs-lookup"><span data-stu-id="62a03-165">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="62a03-166">Defender for Endpoint では、侵害後の動作と検出に基づいてアクションEDRできます。</span><span class="sxs-lookup"><span data-stu-id="62a03-166">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="62a03-167">ブロック モードEDRユーザーのウイルス対策保護に影響を与える可能性がありますか?</span><span class="sxs-lookup"><span data-stu-id="62a03-167">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="62a03-168">EDRモードの場合、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。</span><span class="sxs-lookup"><span data-stu-id="62a03-168">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="62a03-169">EDRウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合は、ブロック モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="62a03-169">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="62a03-170">EDRモードでの動作は、パッシブ モードの[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)Microsoft Defender ウイルス対策 と同様に動作しますが、検出された悪意のあるアーティファクトや動作もブロックおよび修復します。</span><span class="sxs-lookup"><span data-stu-id="62a03-170">EDR in block mode works just like [Microsoft Defender Antivirus in passive mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state), except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span> 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="62a03-171">最新の状態を維持Microsoft Defender ウイルス対策する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="62a03-171">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="62a03-172">悪意のあるMicrosoft Defender ウイルス対策を検出して修復するために、最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a03-172">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="62a03-173">ブロック EDRを有効にするために、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="62a03-173">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="62a03-174">Defender [for Endpoint の機能](https://docs.microsoft.com/windows/security/threat-protection) スタックは、統合された方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="62a03-174">The [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="62a03-175">最適な保護値を取得するには、最新のMicrosoft Defender ウイルス対策する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a03-175">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span>  

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="62a03-176">クラウド保護が必要な理由</span><span class="sxs-lookup"><span data-stu-id="62a03-176">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="62a03-177">デバイスの機能を有効にするには、クラウド保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="62a03-177">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="62a03-178">クラウド保護により [、Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。</span><span class="sxs-lookup"><span data-stu-id="62a03-178">Cloud protection allows [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="62a03-179">パッシブ モードにMicrosoft Defender ウイルス対策設定する方法</span><span class="sxs-lookup"><span data-stu-id="62a03-179">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="62a03-180">「[有効にするMicrosoft Defender ウイルス対策し、パッシブ モードにあるか確認する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="62a03-180">See [Enable Microsoft Defender Antivirus and confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="62a03-181">アクティブまたはパッシブ モードMicrosoft Defender ウイルス対策確認する方法</span><span class="sxs-lookup"><span data-stu-id="62a03-181">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="62a03-182">アクティブ モードまたはパッシブ Microsoft Defender ウイルス対策実行されているかどうかを確認するには、コマンド プロンプトまたは PowerShell を、アクティブ モードで実行しているデバイスでWindows。</span><span class="sxs-lookup"><span data-stu-id="62a03-182">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

#### <a name="use-powershell"></a><span data-ttu-id="62a03-183">PowerShell を使う</span><span class="sxs-lookup"><span data-stu-id="62a03-183">Use PowerShell</span></span>

1. <span data-ttu-id="62a03-184">[スタート] メニューを選択し、入力を開始し、結果 `PowerShell` Windows PowerShellを開きます。</span><span class="sxs-lookup"><span data-stu-id="62a03-184">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="62a03-185">種類`Get-MpComputerStatus`</span><span class="sxs-lookup"><span data-stu-id="62a03-185">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="62a03-186">結果の一覧の **[AMRunningMode]** 行で、次のいずれかの値を探します。</span><span class="sxs-lookup"><span data-stu-id="62a03-186">In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span>
   - <span data-ttu-id="62a03-187">`Normal` - 通常は実行されている Defender サービス。</span><span class="sxs-lookup"><span data-stu-id="62a03-187">`Normal` - Defender service running normally.</span></span> <span data-ttu-id="62a03-188">特別なモードは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="62a03-188">No special modes are enabled.</span></span>
   - <span data-ttu-id="62a03-189">`Passive Mode`- 組織で Microsoft Defender for Endpoint を Microsoft 以外のウイルス対策/マルウェア対策ソリューションと組み合わせて使用している場合は、Microsoft Defender ウイルス対策パッシブ モードに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="62a03-189">`Passive Mode` - If your organization is using Microsoft Defender for Endpoint together with a non-Microsoft antivirus/antimalware solution, then Microsoft Defender Antivirus automatically goes into passive mode.</span></span> <span data-ttu-id="62a03-190">(リアルタイムの保護と脅威は、ユーザーによって修復Microsoft Defender ウイルス対策)。</span><span class="sxs-lookup"><span data-stu-id="62a03-190">(Real-time protection and threats are not remediated by Microsoft Defender Antivirus.)</span></span>
   - <span data-ttu-id="62a03-191">`SxS Passive Mode`- パッシブ モードに似ていますが、制限付き定期的なスキャンを有効にするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="62a03-191">`SxS Passive Mode`- Similar to passive mode, but with the option to turn on limited periodic scanning.</span></span>
   
<span data-ttu-id="62a03-192">詳細については [、「Get-MpComputerStatus」を参照してください](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="62a03-192">To learn more, see [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).</span></span>

#### <a name="use-command-prompt"></a><span data-ttu-id="62a03-193">コマンド プロンプトの使用</span><span class="sxs-lookup"><span data-stu-id="62a03-193">Use Command Prompt</span></span>

1. <span data-ttu-id="62a03-194">[スタート] メニューを選択し、入力を開始し、結果 `Command Prompt` Windowsコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="62a03-194">Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span>

2. <span data-ttu-id="62a03-195">種類`sc query windefend`</span><span class="sxs-lookup"><span data-stu-id="62a03-195">Type `sc query windefend`.</span></span>

3. <span data-ttu-id="62a03-196">結果の一覧の STATE **行で、** サービスが実行されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a03-196">In the list of results, in the **STATE** row, confirm that the service is running.</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="62a03-197">ブロック モードで無効にEDRにどのくらいの時間が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="62a03-197">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="62a03-198">ブロック モードで EDRを無効にした場合、システムがこの機能を無効にするには最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="62a03-198">If you chose to disable EDR in block mode it can take up to 30 minutes for the system to disable this capability.</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="62a03-199">ブロック EDRは、ブロック モードでサポートWindows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="62a03-199">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="62a03-200">いいえ。</span><span class="sxs-lookup"><span data-stu-id="62a03-200">No.</span></span> <span data-ttu-id="62a03-201">EDRモードの場合、次のバージョンのブロック モードがサポートWindows。</span><span class="sxs-lookup"><span data-stu-id="62a03-201">EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="62a03-202">Windows 10 (すべてのリリース)</span><span class="sxs-lookup"><span data-stu-id="62a03-202">Windows 10 (all releases)</span></span>
- <span data-ttu-id="62a03-203">Windowsサーバー、バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="62a03-203">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="62a03-204">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="62a03-204">Windows Server 2019</span></span> 

## <a name="see-also"></a><span data-ttu-id="62a03-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="62a03-205">See also</span></span>

- [<span data-ttu-id="62a03-206">Tech Communityブログ: ブロック モードでのEDRの導入: トラックでの攻撃の停止</span><span class="sxs-lookup"><span data-stu-id="62a03-206">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="62a03-207">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="62a03-207">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)
- [<span data-ttu-id="62a03-208">ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62a03-208">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

