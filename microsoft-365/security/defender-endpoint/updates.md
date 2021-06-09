---
title: Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理する
description: 段階的な更新プロセスとコントロールの詳細
keywords: 更新、更新プロセス、コントロール、リリース
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 435a77432caa9d7335a22993f85cae69eff6cd38
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841764"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="099e8-104">Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理する</span><span class="sxs-lookup"><span data-stu-id="099e8-104">Manage the gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="099e8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="099e8-105">**Applies to:**</span></span>

- [<span data-ttu-id="099e8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="099e8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="099e8-107">重要な保護機能を提供し、攻撃を防止するには、クライアント コンポーネントが最新の状態にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="099e8-107">It is important to ensure that client components are up-to-date to deliver critical protection capabilities and prevent attacks.</span></span>

<span data-ttu-id="099e8-108">機能は、次の複数のコンポーネントを介して提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-108">Capabilities are provided through several components:</span></span> 

- [<span data-ttu-id="099e8-109">エンドポイント検出&応答</span><span class="sxs-lookup"><span data-stu-id="099e8-109">Endpoint Detection & Response</span></span>](overview-endpoint-detection-response.md) 
- <span data-ttu-id="099e8-110">[クラウドによる保護による](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection)[次世代の保護](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="099e8-110">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md)</span></span> 
- [<span data-ttu-id="099e8-111">攻撃表面の縮小</span><span class="sxs-lookup"><span data-stu-id="099e8-111">Attack Surface Reduction</span></span>](overview-attack-surface-reduction.md)

<span data-ttu-id="099e8-112">更新プログラムは、段階的なリリース プロセスを使用して毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="099e8-112">Updates are released monthly using a gradual release process.</span></span> <span data-ttu-id="099e8-113">このプロセスは、早期障害検出が発生した時点で影響をキャッチし、大規模なロールアウトの前に迅速に対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="099e8-113">This process helps to enable early failure detection to catch impact as it occurs and address it quickly before a larger rollout.</span></span> 

> [!NOTE]
> <span data-ttu-id="099e8-114">日次定義の更新を制御する方法の詳細については、「定義の更新をスケジュールする - Microsoft Defender ウイルス対策[のWindowsを参照|Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md).定義の更新により、クラウドによる保護がエンドポイントで利用できない場合でも、次世代の保護が新しい脅威から防御されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-114">For more information on how to control daily definition updates, see [Schedule Microsoft Defender Antivirus definition updates - Windows security | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definition updates ensure that next-generation protection can defend against new threats, even if cloud-delivered protection is not available to the endpoint.</span></span>

## <a name="microsoft-gradual-rollout-model"></a><span data-ttu-id="099e8-115">Microsoft 段階的ロールアウト モデル</span><span class="sxs-lookup"><span data-stu-id="099e8-115">Microsoft gradual rollout model</span></span>

<span data-ttu-id="099e8-116">次の段階的ロールアウト モデルに従います。</span><span class="sxs-lookup"><span data-stu-id="099e8-116">The following gradual rollout model is followed:</span></span>

1. <span data-ttu-id="099e8-117">最初のリリースはベータ チャネルのサブスクライバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-117">The first release goes out to Beta channel subscribers.</span></span>
2. <span data-ttu-id="099e8-118">検証、フィードバック、および修正が完了すると、段階的なロールアウト プロセスが調整された方法で開始され、最初にチャネルサブスクライバーをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="099e8-118">After validation, feedback, and fixes, we start the gradual rollout process in a throttled way and to Preview channel subscribers first.</span></span>
3. <span data-ttu-id="099e8-119">その後、グローバル人口の残りの部分への更新プログラムのリリースに進み、10 ~ 100% のスケール アウトを行います。</span><span class="sxs-lookup"><span data-stu-id="099e8-119">We then proceed to release the update to the rest of the global population, scaling out from 10-100%.</span></span>

<span data-ttu-id="099e8-120">エンジニアは継続的に影響を監視し、問題をエスカレートして、必要に応じて修正プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="099e8-120">Our engineers continuously monitor impact and escalate any issues to create a fix as needed.</span></span>

## <a name="how-to-customize-your-internal-deployment-process"></a><span data-ttu-id="099e8-121">内部展開プロセスをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="099e8-121">How to customize your internal deployment process</span></span>

<span data-ttu-id="099e8-122">コンピューターが Windows Update から Defender 更新プログラムを受け取っている場合、段階的なロールアウトプロセスによって、一部のコンピューターが他のコンピューターよりも早く Defender 更新プログラムを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="099e8-122">If your machines are receiving Defender updates from Windows Update, the gradual rollout process may result in some of your machines receiving Defender updates sooner than others.</span></span> <span data-ttu-id="099e8-123">次のセクションでは、更新プログラム チャネル構成を活用して、自動更新を特定のデバイス グループに異なる方法でフローできる戦略を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="099e8-123">The following section explains how to define a strategy that will allow automatic updates to flow differently to specific groups of devices by leveraging update channel configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="099e8-124">独自の段階的なリリースを計画する場合は、プレビュー チャネルと段階的チャネルに登録されているデバイスを常に選択してください。</span><span class="sxs-lookup"><span data-stu-id="099e8-124">When planning for your own gradual release, please make sure to always have a selection of devices subscribed to the preview and staged channels.</span></span> <span data-ttu-id="099e8-125">これにより、組織と Microsoft が環境固有の問題を防止または見つけて修正する機会が提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-125">This will provide your organization as well as Microsoft the opportunity to prevent or find and fix issues specific to your environment.</span></span>

<span data-ttu-id="099e8-126">Windows Server Update Services (WSUS) や Microsoft Endpoint Configuration Manager (MECM) などの更新プログラムを受け取るコンピューターの場合、Microsoft Defender for Endpoint のオプションを含め、Windows のすべての更新プログラムに対してさらに多くのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-126">For machines receiving updates through, for example, Windows Server Update Services (WSUS) or Microsoft Endpoint Configuration Manager (MECM), more options are available to all Windows updates, including options  for Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="099e8-127">WSUS、MECM のようなソリューションを使用して更新プログラムの配布とアプリケーションを管理する方法の詳細については、「Microsoft Defender ウイルス対策 更新プログラムの管理とベースラインの適用 - Windows セキュリティ | [Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span><span class="sxs-lookup"><span data-stu-id="099e8-127">Read more about how to use a solution like WSUS, MECM to manage the distribution and application of updates at [Manage Microsoft Defender Antivirus updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span></span>

## <a name="update-channels-for-monthly-updates"></a><span data-ttu-id="099e8-128">月次更新プログラムのチャネルを更新する</span><span class="sxs-lookup"><span data-stu-id="099e8-128">Update channels for monthly updates</span></span>

<span data-ttu-id="099e8-129">コンピューターを更新チャネルに割り当て、コンピューターが毎月エンジンとプラットフォームの更新プログラムを受け取るケイデンスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-129">You can assign a machine to an update channel to define the cadence in which a machine receives monthly engine and platform updates.</span></span>

<span data-ttu-id="099e8-130">更新プログラムを構成する方法の詳細については、「Microsoft Defender 更新プログラムのカスタム段階的ロールアウト プロセスを作成する」 [を参照してください](configure-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="099e8-130">For more information on how to configure updates, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>

<span data-ttu-id="099e8-131">次の更新プログラム チャネルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-131">The following update channels are available:</span></span>

| <span data-ttu-id="099e8-132">チャネル名</span><span class="sxs-lookup"><span data-stu-id="099e8-132">Channel name</span></span>  | <span data-ttu-id="099e8-133">説明</span><span class="sxs-lookup"><span data-stu-id="099e8-133">Description</span></span>  | <span data-ttu-id="099e8-134">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="099e8-134">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="099e8-135">ベータ チャネル - プレリリース</span><span class="sxs-lookup"><span data-stu-id="099e8-135">Beta Channel - Prerelease</span></span>  | <span data-ttu-id="099e8-136">他のユーザーより前に更新プログラムをテストする</span><span class="sxs-lookup"><span data-stu-id="099e8-136">Test updates before others</span></span>  | <span data-ttu-id="099e8-137">このチャネルに設定されたデバイスは、新しい月次更新プログラムを最初に受信します。</span><span class="sxs-lookup"><span data-stu-id="099e8-137">Devices set to this channel will be the first to receive new monthly updates.</span></span> <span data-ttu-id="099e8-138">[ベータ チャネル] を選択して、Microsoft への問題の特定と報告に参加します。</span><span class="sxs-lookup"><span data-stu-id="099e8-138">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="099e8-139">Insider Program Windowsデバイスは、既定でこのチャネルにサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="099e8-139">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="099e8-140">テスト環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-140">For use in test environments only.</span></span>  |
| <span data-ttu-id="099e8-141">最新機能提供チャネル (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="099e8-141">Current Channel (Preview)</span></span>  | <span data-ttu-id="099e8-142">段階的なリリース中に以前に **現在のチャネル** 更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="099e8-142">Get Current Channel updates **earlier** during gradual release</span></span>  | <span data-ttu-id="099e8-143">このチャネルに設定されたデバイスには、段階的なリリース サイクルの最も早い更新プログラムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-143">Devices set to this channel will be offered updates earliest during the gradual release cycle.</span></span> <span data-ttu-id="099e8-144">実稼働前/検証前の環境で推奨されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-144">Suggested for pre-production/validation environments.</span></span>  |
| <span data-ttu-id="099e8-145">現在のチャネル (ステージ)</span><span class="sxs-lookup"><span data-stu-id="099e8-145">Current Channel (Staged)</span></span>  | <span data-ttu-id="099e8-146">段階的なリリース中に後で現在のチャネル更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="099e8-146">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="099e8-147">デバイスは、段階的なリリース サイクル中に後で更新プログラムを提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-147">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="099e8-148">デバイスの母集団の小さな代表的な部分 (~10%)に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="099e8-148">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="099e8-149">現在のチャネル (Broad)</span><span class="sxs-lookup"><span data-stu-id="099e8-149">Current Channel (Broad)</span></span> | <span data-ttu-id="099e8-150">段階的なリリースの最後に更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="099e8-150">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="099e8-151">段階的なリリース サイクルが完了した後にのみ、デバイスに更新プログラムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-151">Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="099e8-152">実稼働人口 (~10~100%)の幅広いデバイスセットに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="099e8-152">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  |
| <span data-ttu-id="099e8-153">(既定)</span><span class="sxs-lookup"><span data-stu-id="099e8-153">(default)</span></span>  |   | <span data-ttu-id="099e8-154">このポリシーを無効にするか構成しない場合、デバイスは現在のチャネル (既定) に残ります。段階的なリリース サイクル中に自動的に最新の状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="099e8-154">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="099e8-155">ほとんどのデバイスに適しています。</span><span class="sxs-lookup"><span data-stu-id="099e8-155">Suitable for most devices.</span></span>  |

### <a name="update-channels-for-daily-definition-updates"></a><span data-ttu-id="099e8-156">毎日の定義更新のチャネルを更新する</span><span class="sxs-lookup"><span data-stu-id="099e8-156">Update channels for daily definition updates</span></span>

<span data-ttu-id="099e8-157">コンピューターを更新チャネルに割り当て、コンピューターが毎日定義の更新を受け取るケイデンスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-157">You can assign a machine to an update channel to define the cadence in which a machine receives daily definition updates.</span></span>
  
| <span data-ttu-id="099e8-158">チャネル名</span><span class="sxs-lookup"><span data-stu-id="099e8-158">Channel name</span></span>  | <span data-ttu-id="099e8-159">説明</span><span class="sxs-lookup"><span data-stu-id="099e8-159">Description</span></span>  | <span data-ttu-id="099e8-160">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="099e8-160">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="099e8-161">現在のチャネル (ステージ)</span><span class="sxs-lookup"><span data-stu-id="099e8-161">Current Channel (Staged)</span></span>  | <span data-ttu-id="099e8-162">段階的なリリース中に後で現在のチャネル更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="099e8-162">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="099e8-163">デバイスは、段階的なリリース サイクル中に後で更新プログラムを提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-163">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="099e8-164">デバイスの母集団の小さな代表的な部分 (~10%)に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="099e8-164">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="099e8-165">現在のチャネル (Broad)</span><span class="sxs-lookup"><span data-stu-id="099e8-165">Current Channel (Broad)</span></span> | <span data-ttu-id="099e8-166">段階的なリリースの最後に更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="099e8-166">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="099e8-167">デバイスは、段階的なリリース サイクルの後に更新プログラムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-167">Devices will be offered updates after the gradual release cycle.</span></span> <span data-ttu-id="099e8-168">制限付き更新プログラムのみを受信するデータセンター コンピューターに最適です。</span><span class="sxs-lookup"><span data-stu-id="099e8-168">Best for datacenter machines that only receive limited updates.</span></span> <span data-ttu-id="099e8-169">注: この設定は、すべての Defender 更新プログラムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-169">Note: this setting applies to all Defender updates.</span></span>  |
| <span data-ttu-id="099e8-170">(既定)</span><span class="sxs-lookup"><span data-stu-id="099e8-170">(default)</span></span>  |   | <span data-ttu-id="099e8-171">このポリシーを無効にするか構成しない場合、デバイスは現在のチャネル (既定) に残ります。段階的なリリース サイクル中に自動的に最新の状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="099e8-171">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="099e8-172">ほとんどのデバイスに適しています</span><span class="sxs-lookup"><span data-stu-id="099e8-172">Suitable for most devices</span></span>  |

> [!NOTE]
> <span data-ttu-id="099e8-173">時間の遅延を利用する代わりに最新の署名を強制的に更新する場合は、まずこのポリシーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="099e8-173">In case you wish to force an update to the newest signature instead of leveraging the time delay, you will need to remove this policy first.</span></span>

## <a name="update-guidance"></a><span data-ttu-id="099e8-174">更新のガイダンス</span><span class="sxs-lookup"><span data-stu-id="099e8-174">Update guidance</span></span>

<span data-ttu-id="099e8-175">ほとんどの場合、Windows Update を使用する場合の推奨される構成は、エンドポイントが受信した際に、毎月の Defender 更新プログラムを受信して適用できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-175">In most cases, the recommended configuration when using Windows Update is to allow endpoints to receive and apply monthly Defender updates as they arrive.</span></span> <span data-ttu-id="099e8-176">これにより、保護と、導入できる変更に関連する可能性のある影響の最適なバランスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="099e8-176">This provides the best balance between protection and possible impact associated with the changes they can introduce.</span></span>

<span data-ttu-id="099e8-177">自動 Defender 更新プログラムの段階的なロールアウトの制御が必要な環境では、展開グループを使用したアプローチを検討してください。</span><span class="sxs-lookup"><span data-stu-id="099e8-177">For environments where there is a need for a more controlled gradual rollout of automatic Defender updates, consider an approach with deployment groups:</span></span>

1. <span data-ttu-id="099e8-178">Insider プログラムWindows参加するか、デバイスのグループをベータ チャネルに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="099e8-178">Participate in the Windows Insider program or assign a group of devices to the Beta Channel.</span></span>
2. <span data-ttu-id="099e8-179">プレビュー チャネル (通常は検証環境) にオプトインするパイロット グループを指定して、新しい更新プログラムを早期に受信します。</span><span class="sxs-lookup"><span data-stu-id="099e8-179">Designate a pilot group that opts-in to Preview Channel, typically validation environments, to receive new updates early.</span></span>
3. <span data-ttu-id="099e8-180">段階的なチャネルからの段階的なロールアウト中に後で更新プログラムを受け取るコンピューターのグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="099e8-180">Designate a group of machines that receive updates later during the gradual rollout from Staged channel.</span></span> <span data-ttu-id="099e8-181">通常、これは人口の約 10% を代表します。</span><span class="sxs-lookup"><span data-stu-id="099e8-181">Typically, this would be a representative ~10% of the population.</span></span>
4. <span data-ttu-id="099e8-182">段階的なリリース サイクルの完了後に更新プログラムを受け取るコンピューターのグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="099e8-182">Designate a group of machines that receive updates after the gradual release cycle completes.</span></span> <span data-ttu-id="099e8-183">これらは通常、重要な実稼働システムです。</span><span class="sxs-lookup"><span data-stu-id="099e8-183">These are typically important production systems.</span></span>

<span data-ttu-id="099e8-184">残りのデバイスの場合、既定の設定では、Microsoft の段階的なロールアウト プロセス中に新しい更新プログラムを受信し、それ以上の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="099e8-184">For the remainder of devices, the default setting is to receive new updates as they arrive during the Microsoft gradual rollout process and no further configuration is required.</span></span> 

<span data-ttu-id="099e8-185">このモデルの採用:</span><span class="sxs-lookup"><span data-stu-id="099e8-185">Adopting this model:</span></span>
- <span data-ttu-id="099e8-186">製品環境に到達する前に早期リリースをテストできます</span><span class="sxs-lookup"><span data-stu-id="099e8-186">Allows you to test early releases before they reach a production environment</span></span> 
- <span data-ttu-id="099e8-187">実稼働環境で定期的な更新プログラムを受け取り、重大な脅威に対する保護を確実に行います。</span><span class="sxs-lookup"><span data-stu-id="099e8-187">Ensure the production environment still receives regular updates and ensure protection against critical threats.</span></span>

## <a name="management-tools"></a><span data-ttu-id="099e8-188">管理ツール</span><span class="sxs-lookup"><span data-stu-id="099e8-188">Management tools</span></span>
<span data-ttu-id="099e8-189">月次更新プログラム用に独自のカスタム段階的ロールアウト プロセスを作成するには、次のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="099e8-189">To create your own custom gradual rollout process for monthly updates, you can use the following tools:</span></span>

- <span data-ttu-id="099e8-190">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="099e8-190">Group policy</span></span>
- <span data-ttu-id="099e8-191">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="099e8-191">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="099e8-192">PowerShell</span><span class="sxs-lookup"><span data-stu-id="099e8-192">PowerShell</span></span>

<span data-ttu-id="099e8-193">これらのツールの使い方の詳細については、「Microsoft Defender 更新プログラムのカスタム段階的ロールアウト プロセスを作成する [」を参照してください](configure-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="099e8-193">For details on how to use these tools, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>
