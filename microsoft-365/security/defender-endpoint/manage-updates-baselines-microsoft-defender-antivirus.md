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
ms.date: 07/12/2021
ms.openlocfilehash: 0179c620c8ba00c987395a800ed335644048283f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394967"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="5ab8f-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="5ab8f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-105">**Applies to:**</span></span>

- [<span data-ttu-id="5ab8f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ab8f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="5ab8f-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="5ab8f-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="5ab8f-108">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="5ab8f-109">パッシブ モードで実行されている場合でも、ウイルス対策Microsoft Defender ウイルス対策[更新してください。](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="5ab8f-110">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="5ab8f-111">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-111">Security intelligence updates</span></span>
- <span data-ttu-id="5ab8f-112">製品の更新</span><span class="sxs-lookup"><span data-stu-id="5ab8f-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="5ab8f-113">最新のエンジン、プラットフォーム、署名の日付を確認するには、セキュリティ インテリジェンスの更新プログラム[(Microsoft Defender ウイルス対策その他の Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)マルウェア対策に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="5ab8f-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-114">Security intelligence updates</span></span>

<span data-ttu-id="5ab8f-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab8f-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="5ab8f-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="5ab8f-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="5ab8f-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="5ab8f-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="5ab8f-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="5ab8f-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="5ab8f-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="5ab8f-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="5ab8f-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="5ab8f-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="5ab8f-124">Product updates</span></span>

<span data-ttu-id="5ab8f-125">Microsoft Defender ウイルス対策プラットフォーム更新 [プログラムと呼ばれる月次更新プログラム (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *が必要です*。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="5ab8f-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="5ab8f-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="5ab8f-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5ab8f-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="5ab8f-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="5ab8f-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="5ab8f-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="5ab8f-132">この記事では、広範なリリース チャネルに含まれる変更の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="5ab8f-133">[最新の広範なチャネル リリースについては、こちらを参照してください](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="5ab8f-134">段階的なロールアウト プロセスの詳細、および次のリリースの詳細については、「Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの管理」 [を参照してください](manage-gradual-rollout.md)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="5ab8f-135">セキュリティ インテリジェンスの更新プログラムの詳細については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="5ab8f-136">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="5ab8f-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="5ab8f-137">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="5ab8f-138">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="5ab8f-138">All our updates contain</span></span> 
- <span data-ttu-id="5ab8f-139">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-139">performance improvements;</span></span>
- <span data-ttu-id="5ab8f-140">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="5ab8f-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="5ab8f-141">統合の改善 (クラウド[、Microsoft 365 Defender)。](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="5ab8f-142">2021 年 6 月 (プラットフォーム: 4.18.2106.5 |エンジン: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="5ab8f-143">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="5ab8f-144">&ensp;リリース: **2021 年 6 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="5ab8f-145">&ensp;プラットフォーム: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="5ab8f-146">&ensp;エンジン: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="5ab8f-147">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-148">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-148">What's new</span></span>
- <span data-ttu-id="5ab8f-149">Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="5ab8f-150">[「Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの管理」を参照してください](manage-gradual-rollout.md)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="5ab8f-151">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="5ab8f-152">マルウェア対策定義のロールアウトの改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="5ab8f-153">拡張エッジ ネットワーク イベント検査</span><span class="sxs-lookup"><span data-stu-id="5ab8f-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-154">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-154">Known Issues</span></span>
<span data-ttu-id="5ab8f-155">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-156">May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="5ab8f-157">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="5ab8f-158">&ensp;リリース: **2021 年 6** 月 3 日</span><span class="sxs-lookup"><span data-stu-id="5ab8f-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="5ab8f-159">&ensp;プラットフォーム: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="5ab8f-160">&ensp;エンジン: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="5ab8f-161">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-162">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-162">What's new</span></span>
- <span data-ttu-id="5ab8f-163">動作監視 [の改善](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="5ab8f-164">固定 [ネットワーク保護通知](network-protection.md) フィルター機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-165">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-165">Known Issues</span></span>
<span data-ttu-id="5ab8f-166">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-167">2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="5ab8f-168">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="5ab8f-169">&ensp;リリース: **2021**  年 4 月 26 日 (エンジン: 1.1.18100.6 リリース 2021 年 5 月 5 日) &ensp; プラットフォーム: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="5ab8f-170">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="5ab8f-171">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-172">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-172">What's new</span></span>
- <span data-ttu-id="5ab8f-173">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="5ab8f-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="5ab8f-174">カーネル モードのキー ロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="5ab8f-175">Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール [が追加されました](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="5ab8f-176">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-176">Known Issues</span></span>
<span data-ttu-id="5ab8f-177">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="5ab8f-178">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="5ab8f-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="5ab8f-179">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="5ab8f-180">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="5ab8f-181">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="5ab8f-182">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="5ab8f-183">&ensp;リリース: **2021 年 4 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="5ab8f-184">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="5ab8f-185">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="5ab8f-186">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-187">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-187">What's new</span></span>

- <span data-ttu-id="5ab8f-188">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="5ab8f-189">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="5ab8f-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="5ab8f-190">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="5ab8f-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-191">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-191">Known Issues</span></span>
<span data-ttu-id="5ab8f-192">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-193">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="5ab8f-194">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="5ab8f-195">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="5ab8f-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="5ab8f-196">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="5ab8f-197">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="5ab8f-198">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-199">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-199">What's new</span></span>

- <span data-ttu-id="5ab8f-200">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="5ab8f-201">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="5ab8f-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-202">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-202">Known Issues</span></span>
<span data-ttu-id="5ab8f-203">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-204">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="5ab8f-205">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="5ab8f-206">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="5ab8f-207">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="5ab8f-208">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="5ab8f-209">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-210">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-210">What's new</span></span>

- <span data-ttu-id="5ab8f-211">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="5ab8f-212">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="5ab8f-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="5ab8f-213">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="5ab8f-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="5ab8f-214">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="5ab8f-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="5ab8f-215">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="5ab8f-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-216">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-216">Known Issues</span></span>
<span data-ttu-id="5ab8f-217">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-218">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="5ab8f-219">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="5ab8f-220">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="5ab8f-221">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="5ab8f-222">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="5ab8f-223">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-224">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-224">What's new</span></span>

- <span data-ttu-id="5ab8f-225">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-226">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-226">Known Issues</span></span>
<span data-ttu-id="5ab8f-227">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-228">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="5ab8f-229">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="5ab8f-230">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="5ab8f-231">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="5ab8f-232">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="5ab8f-233">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-234">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-234">What's new</span></span>

- <span data-ttu-id="5ab8f-235">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="5ab8f-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="5ab8f-236">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="5ab8f-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="5ab8f-237">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="5ab8f-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="5ab8f-238">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="5ab8f-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-239">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-239">Known Issues</span></span>

<span data-ttu-id="5ab8f-240">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5ab8f-241">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="5ab8f-242">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="5ab8f-243">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="5ab8f-244">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="5ab8f-245">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="5ab8f-246">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-247">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-247">What's new</span></span>

- <span data-ttu-id="5ab8f-248">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="5ab8f-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="5ab8f-249">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="5ab8f-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="5ab8f-250">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="5ab8f-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="5ab8f-251">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ab8f-251">New management interfaces for:</span></span>
   - <span data-ttu-id="5ab8f-252">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="5ab8f-252">UDP Inspection</span></span>
   - <span data-ttu-id="5ab8f-253">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="5ab8f-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="5ab8f-254">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="5ab8f-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="5ab8f-255">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="5ab8f-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="5ab8f-256">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-257">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-257">Known Issues</span></span>

<span data-ttu-id="5ab8f-258">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="5ab8f-259">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="5ab8f-260">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="5ab8f-261">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="5ab8f-262">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="5ab8f-263">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="5ab8f-264">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="5ab8f-265">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-265">What's new</span></span>

- <span data-ttu-id="5ab8f-266">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="5ab8f-266">Add more telemetry events</span></span>
- <span data-ttu-id="5ab8f-267">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="5ab8f-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="5ab8f-268">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="5ab8f-269">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="5ab8f-270">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="5ab8f-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="5ab8f-271">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="5ab8f-272">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="5ab8f-273">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-273">Known Issues</span></span>
<span data-ttu-id="5ab8f-274">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-275">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="5ab8f-276">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="5ab8f-277">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="5ab8f-278">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="5ab8f-279">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="5ab8f-280">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-281">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-281">What's new</span></span>

- <span data-ttu-id="5ab8f-282">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="5ab8f-283">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-284">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-284">Known Issues</span></span>
<span data-ttu-id="5ab8f-285">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-286">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="5ab8f-287">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="5ab8f-288">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="5ab8f-289">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="5ab8f-290">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="5ab8f-291">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-292">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-292">What's new</span></span>

- <span data-ttu-id="5ab8f-293">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="5ab8f-294">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="5ab8f-295">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="5ab8f-296">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="5ab8f-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="5ab8f-297">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="5ab8f-297">Fixed registry query</span></span> 
- <span data-ttu-id="5ab8f-298">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="5ab8f-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-299">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-299">Known Issues</span></span>
<span data-ttu-id="5ab8f-300">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-301">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="5ab8f-302">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="5ab8f-303">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="5ab8f-304">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="5ab8f-305">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="5ab8f-306">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-307">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-307">What's new</span></span>

- <span data-ttu-id="5ab8f-308">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="5ab8f-308">Improved logging for scan events</span></span>
- <span data-ttu-id="5ab8f-309">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="5ab8f-310">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="5ab8f-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="5ab8f-311">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="5ab8f-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="5ab8f-312">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="5ab8f-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="5ab8f-313">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="5ab8f-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-314">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-314">Known Issues</span></span>
<span data-ttu-id="5ab8f-315">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-316">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="5ab8f-317">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="5ab8f-318">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="5ab8f-319">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="5ab8f-320">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="5ab8f-321">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-322">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-322">What's new</span></span>
- <span data-ttu-id="5ab8f-323">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="5ab8f-323">WDfilter improvements</span></span>
- <span data-ttu-id="5ab8f-324">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="5ab8f-325">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="5ab8f-326">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="5ab8f-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="5ab8f-327">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="5ab8f-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="5ab8f-328">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-328">UEFI scan capability</span></span>
- <span data-ttu-id="5ab8f-329">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="5ab8f-330">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-330">Known Issues</span></span>
<span data-ttu-id="5ab8f-331">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-332">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="5ab8f-333">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="5ab8f-334">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="5ab8f-335">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="5ab8f-336">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="5ab8f-337">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5ab8f-338">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-338">What's new</span></span>

- <span data-ttu-id="5ab8f-339">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="5ab8f-340">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="5ab8f-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="5ab8f-341">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="5ab8f-342">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="5ab8f-343">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5ab8f-344">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-344">Known Issues</span></span>
<span data-ttu-id="5ab8f-345">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="5ab8f-346">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="5ab8f-347">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="5ab8f-348">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="5ab8f-349">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="5ab8f-350">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="5ab8f-351">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="5ab8f-352">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="5ab8f-353">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-353">Known Issues</span></span>
<span data-ttu-id="5ab8f-354">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="5ab8f-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-355">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="5ab8f-356">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="5ab8f-357">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="5ab8f-358">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="5ab8f-359">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="5ab8f-360">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="5ab8f-361">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-361">What's new</span></span>

- <span data-ttu-id="5ab8f-362">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="5ab8f-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="5ab8f-363">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="5ab8f-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="5ab8f-364">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="5ab8f-365">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="5ab8f-366">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="5ab8f-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5ab8f-367">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-367">Known Issues</span></span>

<span data-ttu-id="5ab8f-368">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="5ab8f-369">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="5ab8f-370">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-370">This update is:</span></span>
> - <span data-ttu-id="5ab8f-371">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="5ab8f-372">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="5ab8f-373">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="5ab8f-374">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="5ab8f-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="5ab8f-375">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="5ab8f-376">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="5ab8f-377">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="5ab8f-378">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="5ab8f-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="5ab8f-379">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="5ab8f-380">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="5ab8f-381">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="5ab8f-382">新機能</span><span class="sxs-lookup"><span data-stu-id="5ab8f-382">What's new</span></span>

- <span data-ttu-id="5ab8f-383">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="5ab8f-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="5ab8f-384">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="5ab8f-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="5ab8f-385">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="5ab8f-386">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5ab8f-387">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5ab8f-387">Known Issues</span></span>
<span data-ttu-id="5ab8f-388">この更新プログラムをインストールすると、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.18.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="5ab8f-389">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="5ab8f-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="5ab8f-390">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="5ab8f-391">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="5ab8f-392">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="5ab8f-393">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="5ab8f-394">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="5ab8f-395">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="5ab8f-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="5ab8f-396">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="5ab8f-397">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="5ab8f-398">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="5ab8f-399">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="5ab8f-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="5ab8f-400">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="5ab8f-401">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="5ab8f-401">Windows 10 release</span></span>  |<span data-ttu-id="5ab8f-402">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="5ab8f-402">Platform version</span></span>  |<span data-ttu-id="5ab8f-403">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="5ab8f-403">Engine version</span></span> |<span data-ttu-id="5ab8f-404">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="5ab8f-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="5ab8f-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="5ab8f-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="5ab8f-406">4.18.1909.6</span></span> |<span data-ttu-id="5ab8f-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="5ab8f-407">1.1.17000.2</span></span> | <span data-ttu-id="5ab8f-408">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-409">1909  (19H2)</span></span> |<span data-ttu-id="5ab8f-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="5ab8f-410">4.18.1902.5</span></span> |<span data-ttu-id="5ab8f-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="5ab8f-411">1.1.16700.3</span></span> | <span data-ttu-id="5ab8f-412">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-413">1903  (19H1)</span></span> |<span data-ttu-id="5ab8f-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="5ab8f-414">4.18.1902.5</span></span> |<span data-ttu-id="5ab8f-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="5ab8f-415">1.1.15600.4</span></span> | <span data-ttu-id="5ab8f-416">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-417">1809  (RS5)</span></span> |<span data-ttu-id="5ab8f-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="5ab8f-418">4.18.1807.18075</span></span> |<span data-ttu-id="5ab8f-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="5ab8f-419">1.1.15000.2</span></span> | <span data-ttu-id="5ab8f-420">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-421">1803  (RS4)</span></span> |<span data-ttu-id="5ab8f-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="5ab8f-422">4.13.17134.1</span></span> |<span data-ttu-id="5ab8f-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="5ab8f-423">1.1.14600.4</span></span> | <span data-ttu-id="5ab8f-424">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-425">1709  (RS3)</span></span> |<span data-ttu-id="5ab8f-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="5ab8f-426">4.12.16299.15</span></span> |<span data-ttu-id="5ab8f-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="5ab8f-427">1.1.14104.0</span></span> | <span data-ttu-id="5ab8f-428">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-429">1703  (RS2)</span></span> |<span data-ttu-id="5ab8f-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="5ab8f-430">4.11.15603.2</span></span> |<span data-ttu-id="5ab8f-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="5ab8f-431">1.1.13504.0</span></span> | <span data-ttu-id="5ab8f-432">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5ab8f-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-433">1607 (RS1)</span></span> |<span data-ttu-id="5ab8f-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="5ab8f-434">4.10.14393.3683</span></span> |<span data-ttu-id="5ab8f-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="5ab8f-435">1.1.12805.0</span></span> | <span data-ttu-id="5ab8f-436">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="5ab8f-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="5ab8f-437">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="5ab8f-438">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="5ab8f-439">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="5ab8f-440">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="5ab8f-441">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="5ab8f-442">1.1.2107.02</span><span class="sxs-lookup"><span data-stu-id="5ab8f-442">1.1.2107.02</span></span></summary>

<span data-ttu-id="5ab8f-443">&ensp;パッケージのバージョン: **1.1.2107.02**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-443">&ensp;Package version: **1.1.2107.02**  </span></span>  
<span data-ttu-id="5ab8f-444">&ensp;プラットフォーム のバージョン: **4.18.2105.5** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-444">&ensp;Platform version: **4.18.2105.5** </span></span>  
<span data-ttu-id="5ab8f-445">&ensp;エンジンのバージョン: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-445">&ensp;Engine version: **1.1.18300.4**</span></span>  
<span data-ttu-id="5ab8f-446">&ensp;署名バージョン: **1.343.658.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-446">&ensp;Signature version: **1.343.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-447">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-447">Fixes</span></span>
- <span data-ttu-id="5ab8f-448">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-449">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-449">Additional information</span></span>
- <span data-ttu-id="5ab8f-450">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-451">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="5ab8f-451">1.1.2106.01</span></span></summary>

<span data-ttu-id="5ab8f-452">&ensp;パッケージ のバージョン: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-452">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="5ab8f-453">&ensp;プラットフォーム のバージョン: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-453">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="5ab8f-454">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="5ab8f-455">&ensp;署名バージョン: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-455">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-456">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-456">Fixes</span></span>
- <span data-ttu-id="5ab8f-457">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-458">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-458">Additional information</span></span>
- <span data-ttu-id="5ab8f-459">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-460">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="5ab8f-460">1.1.2105.01</span></span></summary>

<span data-ttu-id="5ab8f-461">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-461">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="5ab8f-462">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-462">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="5ab8f-463">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-463">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="5ab8f-464">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-464">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-465">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-465">Fixes</span></span>
- <span data-ttu-id="5ab8f-466">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-467">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-467">Additional information</span></span>
- <span data-ttu-id="5ab8f-468">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-469">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="5ab8f-469">1.1.2104.01</span></span></summary>

<span data-ttu-id="5ab8f-470">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-470">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="5ab8f-471">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-471">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="5ab8f-472">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-472">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="5ab8f-473">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-473">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-474">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-474">Fixes</span></span>
- <span data-ttu-id="5ab8f-475">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-476">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-476">Additional information</span></span>
- <span data-ttu-id="5ab8f-477">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-478">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="5ab8f-478">1.1.2103.01</span></span></summary>

<span data-ttu-id="5ab8f-479">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-479">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="5ab8f-480">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-480">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="5ab8f-481">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="5ab8f-482">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-482">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-483">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-483">Fixes</span></span>
- <span data-ttu-id="5ab8f-484">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-485">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-485">Additional information</span></span>
- <span data-ttu-id="5ab8f-486">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-487">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="5ab8f-487">1.1.2102.03</span></span></summary>

<span data-ttu-id="5ab8f-488">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-488">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="5ab8f-489">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="5ab8f-490">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-490">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="5ab8f-491">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-491">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-492">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-492">Fixes</span></span>
- <span data-ttu-id="5ab8f-493">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-494">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-494">Additional information</span></span>
- <span data-ttu-id="5ab8f-495">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-496">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="5ab8f-496">1.1.2101.02</span></span></summary>

<span data-ttu-id="5ab8f-497">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-497">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="5ab8f-498">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-498">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="5ab8f-499">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-499">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="5ab8f-500">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-500">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-501">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-501">Fixes</span></span>
- <span data-ttu-id="5ab8f-502">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-503">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-503">Additional information</span></span>
- <span data-ttu-id="5ab8f-504">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-505">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="5ab8f-505">1.1.2012.01</span></span></summary>

<span data-ttu-id="5ab8f-506">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-506">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="5ab8f-507">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="5ab8f-508">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5ab8f-509">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-509">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-510">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-510">Fixes</span></span>
- <span data-ttu-id="5ab8f-511">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-512">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-512">Additional information</span></span>
- <span data-ttu-id="5ab8f-513">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-513">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-514">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="5ab8f-514">1.1.2011.02</span></span></summary>

<span data-ttu-id="5ab8f-515">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-515">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="5ab8f-516">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-516">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="5ab8f-517">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5ab8f-518">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-518">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-519">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-519">Fixes</span></span>
- <span data-ttu-id="5ab8f-520">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-521">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-521">Additional information</span></span>
- <span data-ttu-id="5ab8f-522">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="5ab8f-522">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-523">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="5ab8f-523">1.1.2011.01</span></span></summary>

<span data-ttu-id="5ab8f-524">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="5ab8f-525">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-525">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="5ab8f-526">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-526">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5ab8f-527">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-527">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-528">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-528">Fixes</span></span>
- <span data-ttu-id="5ab8f-529">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-530">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-530">Additional information</span></span>
- <span data-ttu-id="5ab8f-531">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-531">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5ab8f-532">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="5ab8f-532">1.1.2009.10</span></span></summary>

<span data-ttu-id="5ab8f-533">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="5ab8f-533">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="5ab8f-534">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="5ab8f-534">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="5ab8f-535">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-535">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="5ab8f-536">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="5ab8f-536">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5ab8f-537">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-537">Fixes</span></span>
- <span data-ttu-id="5ab8f-538">なし</span><span class="sxs-lookup"><span data-stu-id="5ab8f-538">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5ab8f-539">追加情報</span><span class="sxs-lookup"><span data-stu-id="5ab8f-539">Additional information</span></span>
- <span data-ttu-id="5ab8f-540">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-540">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="5ab8f-541">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="5ab8f-541">Additional resources</span></span>

| <span data-ttu-id="5ab8f-542">記事</span><span class="sxs-lookup"><span data-stu-id="5ab8f-542">Article</span></span> | <span data-ttu-id="5ab8f-543">説明</span><span class="sxs-lookup"><span data-stu-id="5ab8f-543">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="5ab8f-544">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="5ab8f-544">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="5ab8f-545">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-545">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="5ab8f-546">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-546">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="5ab8f-547">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-547">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="5ab8f-548">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-548">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="5ab8f-549">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="5ab8f-549">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="5ab8f-550">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-550">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="5ab8f-551">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-551">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="5ab8f-552">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-552">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="5ab8f-553">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-553">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="5ab8f-554">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-554">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="5ab8f-555">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="5ab8f-555">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="5ab8f-556">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-556">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
