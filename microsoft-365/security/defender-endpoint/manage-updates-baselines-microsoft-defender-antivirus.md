---
title: 更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する
description: 保護と製品Microsoft Defender ウイルス対策受け取る方法を管理します。
keywords: 更新プログラム、セキュリティ 基準、保護、更新のスケジュール、強制的な更新、モバイル更新、wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314466"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="b5746-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="b5746-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="b5746-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b5746-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5746-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b5746-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="b5746-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="b5746-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="b5746-108">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="b5746-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="b5746-109">パッシブ モードで実行されている場合でも、ウイルス対策Microsoft Defender ウイルス対策[更新してください。](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="b5746-110">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="b5746-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="b5746-111">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-111">Security intelligence updates</span></span>
- <span data-ttu-id="b5746-112">製品の更新</span><span class="sxs-lookup"><span data-stu-id="b5746-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="b5746-113">最新のエンジン、プラットフォーム、署名の日付を確認するには、セキュリティ インテリジェンスの更新プログラム[(Microsoft Defender ウイルス対策その他の Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)マルウェア対策に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5746-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="b5746-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-114">Security intelligence updates</span></span>

<span data-ttu-id="b5746-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5746-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="b5746-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="b5746-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="b5746-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="b5746-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="b5746-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="b5746-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="b5746-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5746-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="b5746-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="b5746-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="b5746-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="b5746-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="b5746-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="b5746-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="b5746-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="b5746-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="b5746-124">Product updates</span></span>

<span data-ttu-id="b5746-125">Microsoft Defender ウイルス対策プラットフォーム更新 [プログラムと呼ばれる月次更新プログラム (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *が必要です*。</span><span class="sxs-lookup"><span data-stu-id="b5746-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="b5746-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="b5746-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="b5746-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="b5746-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="b5746-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b5746-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="b5746-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="b5746-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="b5746-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b5746-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="b5746-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b5746-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="b5746-132">この記事では、広範なリリース チャネルに含まれる変更の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b5746-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="b5746-133">[最新の広範なチャネル リリースについては、こちらを参照してください](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。</span><span class="sxs-lookup"><span data-stu-id="b5746-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="b5746-134">段階的なロールアウト プロセスの詳細、および次のリリースの詳細については、「Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの管理」 [を参照してください](manage-gradual-rollout.md)。</span><span class="sxs-lookup"><span data-stu-id="b5746-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="b5746-135">セキュリティ インテリジェンスの更新プログラムの詳細については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="b5746-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="b5746-136">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="b5746-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="b5746-137">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="b5746-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="b5746-138">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="b5746-138">All our updates contain</span></span> 
- <span data-ttu-id="b5746-139">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="b5746-139">performance improvements;</span></span>
- <span data-ttu-id="b5746-140">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="b5746-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="b5746-141">統合の改善 (クラウド[、Microsoft 365 Defender)。](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="b5746-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="b5746-142">2021 年 6 月 (プラットフォーム: 4.18.2106.5 |エンジン: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="b5746-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="b5746-143">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="b5746-144">&ensp;リリース: **2021 年 6 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="b5746-145">&ensp;プラットフォーム: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="b5746-146">&ensp;エンジン: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="b5746-147">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b5746-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-148">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-148">What's new</span></span>
- <span data-ttu-id="b5746-149">Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール。</span><span class="sxs-lookup"><span data-stu-id="b5746-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="b5746-150">[「Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの管理」を参照してください](manage-gradual-rollout.md)。</span><span class="sxs-lookup"><span data-stu-id="b5746-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="b5746-151">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="b5746-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="b5746-152">マルウェア対策定義のロールアウトの改善</span><span class="sxs-lookup"><span data-stu-id="b5746-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="b5746-153">拡張エッジ ネットワーク イベント検査</span><span class="sxs-lookup"><span data-stu-id="b5746-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-154">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-154">Known Issues</span></span>
<span data-ttu-id="b5746-155">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-156">May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="b5746-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="b5746-157">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="b5746-158">&ensp;リリース: **2021 年 6** 月 3 日</span><span class="sxs-lookup"><span data-stu-id="b5746-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="b5746-159">&ensp;プラットフォーム: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="b5746-160">&ensp;エンジン: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="b5746-161">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b5746-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-162">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-162">What's new</span></span>
- <span data-ttu-id="b5746-163">動作監視 [の改善](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="b5746-164">固定 [ネットワーク保護通知](network-protection.md) フィルター機能</span><span class="sxs-lookup"><span data-stu-id="b5746-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-165">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-165">Known Issues</span></span>
<span data-ttu-id="b5746-166">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-167">2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="b5746-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="b5746-168">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="b5746-169">&ensp;リリース: **2021**  年 4 月 26 日 (エンジン: 1.1.18100.6 リリース 2021 年 5 月 5 日) &ensp; プラットフォーム: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="b5746-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="b5746-170">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="b5746-171">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b5746-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-172">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-172">What's new</span></span>
- <span data-ttu-id="b5746-173">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="b5746-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="b5746-174">カーネル モードのキー ロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="b5746-175">Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール [が追加されました](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="b5746-176">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-176">Known Issues</span></span>
<span data-ttu-id="b5746-177">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="b5746-178">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="b5746-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="b5746-179">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="b5746-180">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="b5746-181">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="b5746-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="b5746-182">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="b5746-183">&ensp;リリース: **2021 年 4 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="b5746-184">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="b5746-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="b5746-185">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="b5746-186">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-187">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-187">What's new</span></span>

- <span data-ttu-id="b5746-188">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="b5746-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="b5746-189">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="b5746-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="b5746-190">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="b5746-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-191">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-191">Known Issues</span></span>
<span data-ttu-id="b5746-192">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-193">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="b5746-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="b5746-194">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="b5746-195">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="b5746-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="b5746-196">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="b5746-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="b5746-197">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="b5746-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="b5746-198">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-199">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-199">What's new</span></span>

- <span data-ttu-id="b5746-200">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="b5746-201">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="b5746-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-202">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-202">Known Issues</span></span>
<span data-ttu-id="b5746-203">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-204">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="b5746-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="b5746-205">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b5746-206">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="b5746-207">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="b5746-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="b5746-208">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="b5746-209">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-210">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-210">What's new</span></span>

- <span data-ttu-id="b5746-211">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="b5746-212">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="b5746-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="b5746-213">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="b5746-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="b5746-214">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="b5746-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="b5746-215">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="b5746-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-216">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-216">Known Issues</span></span>
<span data-ttu-id="b5746-217">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-218">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="b5746-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="b5746-219">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b5746-220">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="b5746-221">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="b5746-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="b5746-222">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="b5746-223">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-224">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-224">What's new</span></span>

- <span data-ttu-id="b5746-225">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-226">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-226">Known Issues</span></span>
<span data-ttu-id="b5746-227">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-228">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="b5746-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="b5746-229">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="b5746-230">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="b5746-231">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="b5746-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="b5746-232">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="b5746-233">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-234">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-234">What's new</span></span>

- <span data-ttu-id="b5746-235">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="b5746-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="b5746-236">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="b5746-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="b5746-237">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="b5746-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="b5746-238">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="b5746-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-239">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-239">Known Issues</span></span>

<span data-ttu-id="b5746-240">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b5746-241">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="b5746-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="b5746-242">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="b5746-243">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="b5746-244">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b5746-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="b5746-245">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="b5746-246">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-247">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-247">What's new</span></span>

- <span data-ttu-id="b5746-248">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="b5746-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="b5746-249">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="b5746-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="b5746-250">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="b5746-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="b5746-251">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5746-251">New management interfaces for:</span></span>
   - <span data-ttu-id="b5746-252">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="b5746-252">UDP Inspection</span></span>
   - <span data-ttu-id="b5746-253">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="b5746-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="b5746-254">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="b5746-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="b5746-255">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="b5746-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="b5746-256">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="b5746-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-257">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-257">Known Issues</span></span>

<span data-ttu-id="b5746-258">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="b5746-259">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="b5746-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="b5746-260">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="b5746-261">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="b5746-262">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="b5746-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="b5746-263">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="b5746-264">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="b5746-265">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-265">What's new</span></span>

- <span data-ttu-id="b5746-266">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="b5746-266">Add more telemetry events</span></span>
- <span data-ttu-id="b5746-267">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="b5746-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="b5746-268">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="b5746-269">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="b5746-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="b5746-270">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="b5746-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="b5746-271">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="b5746-272">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="b5746-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="b5746-273">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-273">Known Issues</span></span>
<span data-ttu-id="b5746-274">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-275">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="b5746-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="b5746-276">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="b5746-277">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="b5746-278">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="b5746-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="b5746-279">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="b5746-280">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-281">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-281">What's new</span></span>

- <span data-ttu-id="b5746-282">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="b5746-283">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-284">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-284">Known Issues</span></span>
<span data-ttu-id="b5746-285">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-286">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="b5746-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="b5746-287">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="b5746-288">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="b5746-289">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="b5746-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="b5746-290">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="b5746-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="b5746-291">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-292">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-292">What's new</span></span>

- <span data-ttu-id="b5746-293">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="b5746-294">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="b5746-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="b5746-295">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="b5746-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="b5746-296">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="b5746-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="b5746-297">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="b5746-297">Fixed registry query</span></span> 
- <span data-ttu-id="b5746-298">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="b5746-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-299">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-299">Known Issues</span></span>
<span data-ttu-id="b5746-300">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-301">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="b5746-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="b5746-302">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="b5746-303">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="b5746-304">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="b5746-305">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="b5746-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="b5746-306">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-307">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-307">What's new</span></span>

- <span data-ttu-id="b5746-308">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="b5746-308">Improved logging for scan events</span></span>
- <span data-ttu-id="b5746-309">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="b5746-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="b5746-310">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="b5746-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="b5746-311">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="b5746-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="b5746-312">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="b5746-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="b5746-313">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="b5746-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-314">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-314">Known Issues</span></span>
<span data-ttu-id="b5746-315">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-316">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="b5746-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="b5746-317">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="b5746-318">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="b5746-319">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="b5746-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="b5746-320">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="b5746-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="b5746-321">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-322">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-322">What's new</span></span>
- <span data-ttu-id="b5746-323">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="b5746-323">WDfilter improvements</span></span>
- <span data-ttu-id="b5746-324">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="b5746-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="b5746-325">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="b5746-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="b5746-326">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="b5746-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="b5746-327">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="b5746-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="b5746-328">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="b5746-328">UEFI scan capability</span></span>
- <span data-ttu-id="b5746-329">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="b5746-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5746-330">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-330">Known Issues</span></span>
<span data-ttu-id="b5746-331">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-332">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="b5746-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="b5746-333">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="b5746-334">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="b5746-335">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="b5746-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="b5746-336">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="b5746-337">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b5746-338">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-338">What's new</span></span>

- <span data-ttu-id="b5746-339">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="b5746-340">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="b5746-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="b5746-341">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="b5746-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="b5746-342">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="b5746-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="b5746-343">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="b5746-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b5746-344">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-344">Known Issues</span></span>
<span data-ttu-id="b5746-345">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="b5746-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="b5746-346">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="b5746-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="b5746-347">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="b5746-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="b5746-348">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="b5746-349">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="b5746-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="b5746-350">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="b5746-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="b5746-351">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b5746-352">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="b5746-353">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-353">Known Issues</span></span>
<span data-ttu-id="b5746-354">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b5746-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-355">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="b5746-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="b5746-356">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="b5746-357">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="b5746-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="b5746-358">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="b5746-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="b5746-359">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="b5746-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="b5746-360">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b5746-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b5746-361">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-361">What's new</span></span>

- <span data-ttu-id="b5746-362">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="b5746-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="b5746-363">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="b5746-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="b5746-364">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="b5746-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="b5746-365">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b5746-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="b5746-366">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="b5746-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b5746-367">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-367">Known Issues</span></span>

<span data-ttu-id="b5746-368">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5746-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="b5746-369">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="b5746-370">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="b5746-370">This update is:</span></span>
> - <span data-ttu-id="b5746-371">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="b5746-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="b5746-372">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="b5746-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="b5746-373">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="b5746-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="b5746-374">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="b5746-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="b5746-375">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="b5746-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b5746-376">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="b5746-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="b5746-377">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="b5746-378">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="b5746-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="b5746-379">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="b5746-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="b5746-380">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="b5746-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="b5746-381">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="b5746-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="b5746-382">新機能</span><span class="sxs-lookup"><span data-stu-id="b5746-382">What's new</span></span>

- <span data-ttu-id="b5746-383">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="b5746-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="b5746-384">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="b5746-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="b5746-385">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="b5746-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="b5746-386">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="b5746-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b5746-387">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5746-387">Known Issues</span></span>
<span data-ttu-id="b5746-388">この更新プログラムをインストールすると、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.18.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5746-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="b5746-389">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="b5746-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="b5746-390">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="b5746-391">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5746-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="b5746-392">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="b5746-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="b5746-393">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="b5746-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="b5746-394">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="b5746-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="b5746-395">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="b5746-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="b5746-396">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="b5746-397">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="b5746-398">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5746-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="b5746-399">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="b5746-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="b5746-400">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="b5746-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="b5746-401">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="b5746-401">Windows 10 release</span></span>  |<span data-ttu-id="b5746-402">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="b5746-402">Platform version</span></span>  |<span data-ttu-id="b5746-403">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="b5746-403">Engine version</span></span> |<span data-ttu-id="b5746-404">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="b5746-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b5746-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="b5746-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="b5746-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="b5746-406">4.18.1909.6</span></span> |<span data-ttu-id="b5746-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="b5746-407">1.1.17000.2</span></span> | <span data-ttu-id="b5746-408">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="b5746-409">1909  (19H2)</span></span> |<span data-ttu-id="b5746-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b5746-410">4.18.1902.5</span></span> |<span data-ttu-id="b5746-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="b5746-411">1.1.16700.3</span></span> | <span data-ttu-id="b5746-412">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="b5746-413">1903  (19H1)</span></span> |<span data-ttu-id="b5746-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b5746-414">4.18.1902.5</span></span> |<span data-ttu-id="b5746-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="b5746-415">1.1.15600.4</span></span> | <span data-ttu-id="b5746-416">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="b5746-417">1809  (RS5)</span></span> |<span data-ttu-id="b5746-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="b5746-418">4.18.1807.18075</span></span> |<span data-ttu-id="b5746-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="b5746-419">1.1.15000.2</span></span> | <span data-ttu-id="b5746-420">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="b5746-421">1803  (RS4)</span></span> |<span data-ttu-id="b5746-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="b5746-422">4.13.17134.1</span></span> |<span data-ttu-id="b5746-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="b5746-423">1.1.14600.4</span></span> | <span data-ttu-id="b5746-424">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="b5746-425">1709  (RS3)</span></span> |<span data-ttu-id="b5746-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="b5746-426">4.12.16299.15</span></span> |<span data-ttu-id="b5746-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="b5746-427">1.1.14104.0</span></span> | <span data-ttu-id="b5746-428">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="b5746-429">1703  (RS2)</span></span> |<span data-ttu-id="b5746-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="b5746-430">4.11.15603.2</span></span> |<span data-ttu-id="b5746-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="b5746-431">1.1.13504.0</span></span> | <span data-ttu-id="b5746-432">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b5746-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="b5746-433">1607 (RS1)</span></span> |<span data-ttu-id="b5746-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="b5746-434">4.10.14393.3683</span></span> |<span data-ttu-id="b5746-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="b5746-435">1.1.12805.0</span></span> | <span data-ttu-id="b5746-436">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b5746-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="b5746-437">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="b5746-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="b5746-438">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="b5746-439">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b5746-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="b5746-440">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b5746-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="b5746-441">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="b5746-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="b5746-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="b5746-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="b5746-443">&ensp;パッケージ のバージョン: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="b5746-444">&ensp;プラットフォーム のバージョン: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="b5746-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="b5746-445">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b5746-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b5746-446">&ensp;署名バージョン: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-447">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-447">Fixes</span></span>
- <span data-ttu-id="b5746-448">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-449">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-449">Additional information</span></span>
- <span data-ttu-id="b5746-450">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="b5746-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="b5746-452">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="b5746-453">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="b5746-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="b5746-454">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b5746-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b5746-455">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-456">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-456">Fixes</span></span>
- <span data-ttu-id="b5746-457">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-458">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-458">Additional information</span></span>
- <span data-ttu-id="b5746-459">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="b5746-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="b5746-461">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="b5746-462">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="b5746-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="b5746-463">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="b5746-464">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-465">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-465">Fixes</span></span>
- <span data-ttu-id="b5746-466">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-467">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-467">Additional information</span></span>
- <span data-ttu-id="b5746-468">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="b5746-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="b5746-470">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="b5746-471">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="b5746-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="b5746-472">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b5746-473">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-474">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-474">Fixes</span></span>
- <span data-ttu-id="b5746-475">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-476">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-476">Additional information</span></span>
- <span data-ttu-id="b5746-477">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="b5746-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="b5746-479">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="b5746-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="b5746-480">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b5746-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b5746-481">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b5746-482">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-483">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-483">Fixes</span></span>
- <span data-ttu-id="b5746-484">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-485">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-485">Additional information</span></span>
- <span data-ttu-id="b5746-486">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="b5746-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="b5746-488">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="b5746-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="b5746-489">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b5746-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b5746-490">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b5746-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="b5746-491">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-492">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-492">Fixes</span></span>
- <span data-ttu-id="b5746-493">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-494">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-494">Additional information</span></span>
- <span data-ttu-id="b5746-495">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="b5746-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="b5746-497">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="b5746-498">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b5746-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b5746-499">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b5746-500">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-501">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-501">Fixes</span></span>
- <span data-ttu-id="b5746-502">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-503">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-503">Additional information</span></span>
- <span data-ttu-id="b5746-504">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="b5746-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="b5746-506">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="b5746-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="b5746-507">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b5746-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b5746-508">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b5746-509">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-510">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-510">Fixes</span></span>
- <span data-ttu-id="b5746-511">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-512">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-512">Additional information</span></span>
- <span data-ttu-id="b5746-513">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="b5746-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="b5746-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="b5746-515">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b5746-516">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b5746-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="b5746-517">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b5746-518">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-519">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-519">Fixes</span></span>
- <span data-ttu-id="b5746-520">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-521">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-521">Additional information</span></span>
- <span data-ttu-id="b5746-522">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b5746-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="b5746-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="b5746-524">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b5746-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b5746-525">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="b5746-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="b5746-526">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b5746-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="b5746-527">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="b5746-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b5746-528">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-528">Fixes</span></span>
- <span data-ttu-id="b5746-529">なし</span><span class="sxs-lookup"><span data-stu-id="b5746-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b5746-530">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="b5746-530">Additional information</span></span>
- <span data-ttu-id="b5746-531">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b5746-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="b5746-532">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="b5746-532">Additional resources</span></span>

| <span data-ttu-id="b5746-533">記事</span><span class="sxs-lookup"><span data-stu-id="b5746-533">Article</span></span> | <span data-ttu-id="b5746-534">説明</span><span class="sxs-lookup"><span data-stu-id="b5746-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="b5746-535">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b5746-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="b5746-536">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5746-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="b5746-537">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="b5746-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="b5746-538">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="b5746-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b5746-539">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="b5746-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="b5746-540">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="b5746-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="b5746-541">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5746-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="b5746-542">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b5746-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="b5746-543">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5746-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="b5746-544">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b5746-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b5746-545">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5746-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="b5746-546">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b5746-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="b5746-547">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5746-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
