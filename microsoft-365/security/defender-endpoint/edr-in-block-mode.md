---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントの検出と応答の詳細
keywords: Microsoft Defender for Endpoint, mde, EDR in block mode, パッシブ モード ブロック
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
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: a2fbb8f1b48dacb27468f8f088f5000da9fcb3b9
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893567"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="7868a-104">ブロック モードでのエンドポイントの検出と応答 (EDR)</span><span class="sxs-lookup"><span data-stu-id="7868a-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7868a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7868a-105">**Applies to:**</span></span>
- [<span data-ttu-id="7868a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7868a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7868a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7868a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7868a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7868a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7868a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7868a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="7868a-110">ブロック モードの EDR とは</span><span class="sxs-lookup"><span data-stu-id="7868a-110">What is EDR in block mode?</span></span>

<span data-ttu-id="7868a-111">[ブロック モードのエンドポイント検出](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) と応答 (EDR) は、Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、悪意のあるアーティファクトからの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="7868a-111">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="7868a-112">オンにすると、ブロック モードの EDR は、デバイスで検出された悪意のあるアーティファクトや動作をブロックします。</span><span class="sxs-lookup"><span data-stu-id="7868a-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="7868a-113">ブロック モードの EDR は、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。</span><span class="sxs-lookup"><span data-stu-id="7868a-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="7868a-114">ブロック モードの EDR は、脆弱性管理の [脅威&統合されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)。</span><span class="sxs-lookup"><span data-stu-id="7868a-114">EDR in block mode is also integrated with [threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="7868a-115">組織のセキュリティ チームは、まだ有効[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)になっていない場合は、ブロック モードで EDR を有効にするセキュリティに関する推奨事項を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7868a-115">Your organization's security team will get a [security recommendation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードで EDR を有効にする推奨事項":::

> [!NOTE]
> <span data-ttu-id="7868a-117">最適な保護を得る場合は、 **[必ず Microsoft Defender for Endpoint ベースラインを展開してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**。</span><span class="sxs-lookup"><span data-stu-id="7868a-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="7868a-118">何かが検出されると何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="7868a-118">What happens when something is detected?</span></span>

<span data-ttu-id="7868a-119">ブロック モードの EDR がオンになっていて、悪意のあるアーティファクトが検出されると、Microsoft Defender for Endpoint は、そのアーティファクトをブロックして修復します。</span><span class="sxs-lookup"><span data-stu-id="7868a-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="7868a-120">アクション センターには、検出の状態が **[ブロック**] または [防止済み] として完了したアクションとして [表示されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)。</span><span class="sxs-lookup"><span data-stu-id="7868a-120">You'll see detection status as **Blocked** or **Prevented** as completed actions in the [Action center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).</span></span>

<span data-ttu-id="7868a-121">次の図は、ブロック モードで EDR を介して検出およびブロックされた望ましくないソフトウェアのインスタンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="7868a-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="ブロック モードの EDR が何かを検出しました":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="7868a-123">ブロック モードで EDR を有効にする</span><span class="sxs-lookup"><span data-stu-id="7868a-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7868a-124">ブロック モード [で](#requirements-for-edr-in-block-mode) EDR をオンにする前に、要件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7868a-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="7868a-125">Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="7868a-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="7868a-126">[設定 **] [**  >  **高度な機能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7868a-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="7868a-127">ブロック モード **で EDR をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="7868a-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="7868a-128">ブロック モードの EDR は、Microsoft Defender セキュリティ センターでのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7868a-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="7868a-129">レジストリ キー、Intune、またはグループ ポリシーを使用して、ブロック モードで EDR を有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7868a-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="7868a-130">ブロック モードでの EDR の要件</span><span class="sxs-lookup"><span data-stu-id="7868a-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="7868a-131">要件</span><span class="sxs-lookup"><span data-stu-id="7868a-131">Requirement</span></span>  |<span data-ttu-id="7868a-132">詳細</span><span class="sxs-lookup"><span data-stu-id="7868a-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="7868a-133">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7868a-133">Permissions</span></span> |<span data-ttu-id="7868a-134">Azure Active Directory で割り当てられたグローバル管理者または [セキュリティ管理者の役割](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="7868a-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="7868a-135">「基本 [アクセス許可」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。</span><span class="sxs-lookup"><span data-stu-id="7868a-135">See [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions).</span></span> |
|<span data-ttu-id="7868a-136">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="7868a-136">Operating system</span></span>     |<span data-ttu-id="7868a-137">次のいずれかのバージョン。</span><span class="sxs-lookup"><span data-stu-id="7868a-137">One of the following versions:</span></span> <br/><span data-ttu-id="7868a-138">- Windows 10 (すべてのリリース)</span><span class="sxs-lookup"><span data-stu-id="7868a-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="7868a-139">- Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="7868a-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="7868a-140">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7868a-140">- Windows Server 2019</span></span>         |
|<span data-ttu-id="7868a-141">Windows E5 登録</span><span class="sxs-lookup"><span data-stu-id="7868a-141">Windows E5 enrollment</span></span>     |<span data-ttu-id="7868a-142">Windows E5 は、次のサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="7868a-142">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="7868a-143">- Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7868a-143">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="7868a-144">- Microsoft 365 E3 と Identity &脅威保護サービス</span><span class="sxs-lookup"><span data-stu-id="7868a-144">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="7868a-145">「[各プランの](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)[コンポーネントと機能」を参照してください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="7868a-145">See [Components](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="7868a-146">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="7868a-146">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="7868a-147">Microsoft Defender ウイルス対策は、アクティブ モードまたはパッシブ モードでインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7868a-147">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="7868a-148">(Microsoft Defender ウイルス対策を Microsoft 以外のウイルス対策ソリューションと共に使用できます。 [Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="7868a-148">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="7868a-149">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="7868a-149">Cloud-delivered protection</span></span> |<span data-ttu-id="7868a-150">Microsoft Defender ウイルス対策がクラウド配信の保護が有効にするように [構成されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="7868a-150">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).</span></span> |
|<span data-ttu-id="7868a-151">Microsoft Defender ウイルス対策クライアント</span><span class="sxs-lookup"><span data-stu-id="7868a-151">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="7868a-152">クライアントが最新の情報に更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7868a-152">Make sure your client is up to date.</span></span> <span data-ttu-id="7868a-153">PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="7868a-153">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="7868a-154">**AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7868a-154">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="7868a-155">Microsoft Defender ウイルス対策エンジン</span><span class="sxs-lookup"><span data-stu-id="7868a-155">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="7868a-156">エンジンが最新の情報に更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7868a-156">Make sure your engine is up to date.</span></span> <span data-ttu-id="7868a-157">PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="7868a-157">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="7868a-158">**AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7868a-158">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="7868a-159">最高の保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外 [が構成されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="7868a-159">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="7868a-160">ブロック モードの EDR は、Microsoft Defender ウイルス対策に定義されている除外を尊重します。</span><span class="sxs-lookup"><span data-stu-id="7868a-160">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7868a-161">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7868a-161">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="7868a-162">デバイスで Microsoft Defender ウイルス対策を実行している場合でも、ブロック モードで EDR をオンにする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="7868a-162">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="7868a-163">Microsoft Defender Antivirus がパッシブ モードまたはアクティブ モードで実行されているかどうかに関して、ブロック モードで EDR をオンに維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7868a-163">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="7868a-164">ブロック モードの EDR は、Microsoft Defender for Endpoint で別の防御層を提供します。</span><span class="sxs-lookup"><span data-stu-id="7868a-164">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7868a-165">これにより、Defender for Endpoint は侵害後の動作 EDR 検出に基づいてアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7868a-165">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="7868a-166">ブロック モードの EDR は、ユーザーのウイルス対策保護に影響を与えますか?</span><span class="sxs-lookup"><span data-stu-id="7868a-166">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="7868a-167">ブロック モードの EDR は、ユーザーのデバイスで実行されているサード パーティ製のウイルス対策保護には影響しません。</span><span class="sxs-lookup"><span data-stu-id="7868a-167">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="7868a-168">ブロック モードの EDR は、プライマリ ウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="7868a-168">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="7868a-169">ブロック モードの EDR は、パッシブ モードの [Microsoft Defender ウイルス](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)対策と同様に動作しますが、検出された悪意のあるアーティファクトや動作もブロックおよび修復します。</span><span class="sxs-lookup"><span data-stu-id="7868a-169">EDR in block mode works just like [Microsoft Defender Antivirus in passive mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state), except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span> 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="7868a-170">Microsoft Defender ウイルス対策を最新の状態に保つ必要がある理由</span><span class="sxs-lookup"><span data-stu-id="7868a-170">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="7868a-171">Microsoft Defender Antivirus は悪意のあるアイテムを検出して修復しますので、最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="7868a-171">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="7868a-172">ブロック モードの EDR を有効にするには、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="7868a-172">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="7868a-173">Defender [for Endpoint の機能](https://docs.microsoft.com/windows/security/threat-protection) スタックは、統合された方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="7868a-173">The [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="7868a-174">最高の保護値を取得するには、Microsoft Defender ウイルス対策を最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="7868a-174">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span>  

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="7868a-175">クラウド保護が必要な理由</span><span class="sxs-lookup"><span data-stu-id="7868a-175">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="7868a-176">デバイスの機能を有効にするには、クラウド保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="7868a-176">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="7868a-177">クラウド保護により [、Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。</span><span class="sxs-lookup"><span data-stu-id="7868a-177">Cloud protection allows [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="7868a-178">Microsoft Defender ウイルス対策をパッシブ モードに設定する方法</span><span class="sxs-lookup"><span data-stu-id="7868a-178">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="7868a-179">「Microsoft [Defender ウイルス対策を有効にする」を参照し、パッシブ モードの状態を確認します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="7868a-179">See [Enable Microsoft Defender Antivirus and confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="7868a-180">Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードにあることを確認する方法</span><span class="sxs-lookup"><span data-stu-id="7868a-180">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="7868a-181">Microsoft Defender Antivirus がアクティブ モードまたはパッシブ モードで実行されているかどうかを確認するには、Windows を実行しているデバイスでコマンド プロンプトまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7868a-181">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

#### <a name="use-powershell"></a><span data-ttu-id="7868a-182">PowerShell を使う</span><span class="sxs-lookup"><span data-stu-id="7868a-182">Use PowerShell</span></span>

1. <span data-ttu-id="7868a-183">[スタート] メニューを選択し、入力を開始し、結果 `PowerShell` Windows PowerShellを開きます。</span><span class="sxs-lookup"><span data-stu-id="7868a-183">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="7868a-184">種類`Get-MpComputerStatus`</span><span class="sxs-lookup"><span data-stu-id="7868a-184">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="7868a-185">結果の一覧の **[AMRunningMode]** 行で、次のいずれかの値を探します。</span><span class="sxs-lookup"><span data-stu-id="7868a-185">In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span>   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

<span data-ttu-id="7868a-186">詳細については [、「Get-MpComputerStatus」を参照してください](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="7868a-186">To learn more, see [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).</span></span>

#### <a name="use-command-prompt"></a><span data-ttu-id="7868a-187">コマンド プロンプトの使用</span><span class="sxs-lookup"><span data-stu-id="7868a-187">Use Command Prompt</span></span>

1. <span data-ttu-id="7868a-188">[スタート] メニューを選択し、入力を `Command Prompt` 開始し、結果で Windows コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7868a-188">Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span>

2. <span data-ttu-id="7868a-189">種類`sc query windefend`</span><span class="sxs-lookup"><span data-stu-id="7868a-189">Type `sc query windefend`.</span></span>

3. <span data-ttu-id="7868a-190">結果の一覧の STATE **行で、** サービスが実行されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="7868a-190">In the list of results, in the **STATE** row, confirm that the service is running.</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="7868a-191">ブロック モードの EDR が無効になるのにどれくらいの時間が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="7868a-191">How much time does it take for EDR in block mode to be disabled?</span></span>
<span data-ttu-id="7868a-192">ブロック モードで EDR を無効にした場合、システムでこの機能を無効にするには最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7868a-192">If you chose to disable EDR in block mode it can take up to 30 minutes for the system to disable this capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="7868a-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="7868a-193">See also</span></span>

- [<span data-ttu-id="7868a-194">Tech Community ブログ: ブロック モードでの EDR の導入: トラックでの攻撃の停止</span><span class="sxs-lookup"><span data-stu-id="7868a-194">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="7868a-195">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="7868a-195">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)
- [<span data-ttu-id="7868a-196">ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7868a-196">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

