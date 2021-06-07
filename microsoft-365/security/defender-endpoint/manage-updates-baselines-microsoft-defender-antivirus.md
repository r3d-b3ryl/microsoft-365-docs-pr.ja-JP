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
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/04/2021
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795984"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="b0ef1-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="b0ef1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-105">**Applies to:**</span></span>

- [<span data-ttu-id="b0ef1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0ef1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="b0ef1-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="b0ef1-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="b0ef1-108">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="b0ef1-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-109">Security intelligence updates</span></span>
- <span data-ttu-id="b0ef1-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="b0ef1-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0ef1-111">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="b0ef1-112">パッシブ モードで実行されている場合でも、Microsoft Defender ウイルス対策保護を[更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="b0ef1-113">最新のエンジン、プラットフォーム、署名日を確認するには、セキュリティ インテリジェンスの更新プログラム (Microsoft Defender ウイルス対策その他の Microsoft マルウェア対策に関する[ページをご覧ください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="b0ef1-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-114">Security intelligence updates</span></span>

<span data-ttu-id="b0ef1-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="b0ef1-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="b0ef1-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="b0ef1-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="b0ef1-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="b0ef1-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="b0ef1-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="b0ef1-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="b0ef1-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="b0ef1-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="b0ef1-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="b0ef1-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="b0ef1-124">Product updates</span></span>

<span data-ttu-id="b0ef1-125">Microsoft Defender ウイルス対策月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、各リリースと共に主要な機能更新プログラムWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="b0ef1-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="b0ef1-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="b0ef1-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b0ef1-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="b0ef1-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="b0ef1-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="b0ef1-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="b0ef1-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="b0ef1-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="b0ef1-133">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="b0ef1-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="b0ef1-134">All our updates contain</span></span> 
- <span data-ttu-id="b0ef1-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-135">performance improvements;</span></span>
- <span data-ttu-id="b0ef1-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="b0ef1-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="b0ef1-137">統合の改善 (Cloud、Microsoft 365 [Defender)。](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="b0ef1-138">May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="b0ef1-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="b0ef1-140">&ensp;リリース: **2021 年 6 月 4 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="b0ef1-141">&ensp;プラットフォーム: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="b0ef1-142">&ensp;エンジン: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="b0ef1-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-144">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-144">What's new</span></span>
- <span data-ttu-id="b0ef1-145">動作監視 [の改善](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="b0ef1-146">固定 [ネットワーク保護通知](network-protection.md) フィルター機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-147">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-147">Known Issues</span></span>
<span data-ttu-id="b0ef1-148">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b0ef1-149">2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="b0ef1-150">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="b0ef1-151">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="b0ef1-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b0ef1-152">&ensp;プラットフォーム: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="b0ef1-153">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="b0ef1-154">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-155">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-155">What's new</span></span>
- <span data-ttu-id="b0ef1-156">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="b0ef1-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="b0ef1-157">カーネル モードのキーロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-158">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-158">Known Issues</span></span>
<span data-ttu-id="b0ef1-159">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b0ef1-160">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="b0ef1-161">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="b0ef1-162">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="b0ef1-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b0ef1-163">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="b0ef1-164">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="b0ef1-165">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-166">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-166">What's new</span></span>

- <span data-ttu-id="b0ef1-167">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="b0ef1-168">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="b0ef1-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="b0ef1-169">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="b0ef1-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-170">Known Issues</span></span>
<span data-ttu-id="b0ef1-171">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="b0ef1-172">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="b0ef1-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="b0ef1-173">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="b0ef1-174">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="b0ef1-175">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="b0ef1-176">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="b0ef1-177">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="b0ef1-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="b0ef1-178">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="b0ef1-179">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="b0ef1-180">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-181">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-181">What's new</span></span>

- <span data-ttu-id="b0ef1-182">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="b0ef1-183">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="b0ef1-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-184">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-184">Known Issues</span></span>
<span data-ttu-id="b0ef1-185">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b0ef1-186">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="b0ef1-187">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b0ef1-188">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="b0ef1-189">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="b0ef1-190">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="b0ef1-191">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-192">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-192">What's new</span></span>

- <span data-ttu-id="b0ef1-193">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="b0ef1-194">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="b0ef1-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="b0ef1-195">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="b0ef1-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="b0ef1-196">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="b0ef1-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="b0ef1-197">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="b0ef1-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-198">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-198">Known Issues</span></span>
<span data-ttu-id="b0ef1-199">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b0ef1-200">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="b0ef1-201">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b0ef1-202">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="b0ef1-203">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="b0ef1-204">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="b0ef1-205">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-206">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-206">What's new</span></span>

- <span data-ttu-id="b0ef1-207">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-208">Known Issues</span></span>
<span data-ttu-id="b0ef1-209">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b0ef1-210">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="b0ef1-211">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="b0ef1-212">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="b0ef1-213">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="b0ef1-214">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="b0ef1-215">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-216">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-216">What's new</span></span>

- <span data-ttu-id="b0ef1-217">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="b0ef1-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="b0ef1-218">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="b0ef1-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="b0ef1-219">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="b0ef1-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="b0ef1-220">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="b0ef1-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-221">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-221">Known Issues</span></span>

<span data-ttu-id="b0ef1-222">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b0ef1-223">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="b0ef1-224">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="b0ef1-225">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="b0ef1-226">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="b0ef1-227">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="b0ef1-228">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-229">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-229">What's new</span></span>

- <span data-ttu-id="b0ef1-230">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="b0ef1-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="b0ef1-231">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="b0ef1-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="b0ef1-232">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="b0ef1-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="b0ef1-233">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0ef1-233">New management interfaces for:</span></span>
   - <span data-ttu-id="b0ef1-234">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="b0ef1-234">UDP Inspection</span></span>
   - <span data-ttu-id="b0ef1-235">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="b0ef1-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="b0ef1-236">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="b0ef1-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="b0ef1-237">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="b0ef1-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="b0ef1-238">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-239">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-239">Known Issues</span></span>

<span data-ttu-id="b0ef1-240">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="b0ef1-241">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="b0ef1-242">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="b0ef1-243">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="b0ef1-244">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="b0ef1-245">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="b0ef1-246">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="b0ef1-247">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-247">What's new</span></span>

- <span data-ttu-id="b0ef1-248">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="b0ef1-248">Add more telemetry events</span></span>
- <span data-ttu-id="b0ef1-249">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="b0ef1-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="b0ef1-250">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="b0ef1-251">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="b0ef1-252">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="b0ef1-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="b0ef1-253">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="b0ef1-254">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="b0ef1-255">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-255">Known Issues</span></span>
<span data-ttu-id="b0ef1-256">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-257">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="b0ef1-258">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="b0ef1-259">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="b0ef1-260">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="b0ef1-261">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="b0ef1-262">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-263">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-263">What's new</span></span>

- <span data-ttu-id="b0ef1-264">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="b0ef1-265">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-266">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-266">Known Issues</span></span>
<span data-ttu-id="b0ef1-267">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-268">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="b0ef1-269">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="b0ef1-270">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="b0ef1-271">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="b0ef1-272">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="b0ef1-273">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-274">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-274">What's new</span></span>

- <span data-ttu-id="b0ef1-275">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="b0ef1-276">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="b0ef1-277">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="b0ef1-278">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="b0ef1-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="b0ef1-279">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="b0ef1-279">Fixed registry query</span></span> 
- <span data-ttu-id="b0ef1-280">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="b0ef1-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-281">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-281">Known Issues</span></span>
<span data-ttu-id="b0ef1-282">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-283">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="b0ef1-284">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="b0ef1-285">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="b0ef1-286">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="b0ef1-287">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="b0ef1-288">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-289">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-289">What's new</span></span>

- <span data-ttu-id="b0ef1-290">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="b0ef1-290">Improved logging for scan events</span></span>
- <span data-ttu-id="b0ef1-291">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="b0ef1-292">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="b0ef1-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="b0ef1-293">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="b0ef1-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="b0ef1-294">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="b0ef1-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="b0ef1-295">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="b0ef1-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-296">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-296">Known Issues</span></span>
<span data-ttu-id="b0ef1-297">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-298">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="b0ef1-299">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="b0ef1-300">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="b0ef1-301">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="b0ef1-302">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="b0ef1-303">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-304">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-304">What's new</span></span>
- <span data-ttu-id="b0ef1-305">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="b0ef1-305">WDfilter improvements</span></span>
- <span data-ttu-id="b0ef1-306">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="b0ef1-307">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="b0ef1-308">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="b0ef1-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="b0ef1-309">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="b0ef1-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="b0ef1-310">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-310">UEFI scan capability</span></span>
- <span data-ttu-id="b0ef1-311">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="b0ef1-312">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-312">Known Issues</span></span>
<span data-ttu-id="b0ef1-313">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-314">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="b0ef1-315">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="b0ef1-316">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="b0ef1-317">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="b0ef1-318">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="b0ef1-319">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b0ef1-320">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-320">What's new</span></span>

- <span data-ttu-id="b0ef1-321">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="b0ef1-322">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="b0ef1-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="b0ef1-323">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="b0ef1-324">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="b0ef1-325">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b0ef1-326">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-326">Known Issues</span></span>
<span data-ttu-id="b0ef1-327">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="b0ef1-328">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="b0ef1-329">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="b0ef1-330">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="b0ef1-331">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="b0ef1-332">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="b0ef1-333">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b0ef1-334">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="b0ef1-335">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-335">Known Issues</span></span>
<span data-ttu-id="b0ef1-336">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b0ef1-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-337">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="b0ef1-338">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="b0ef1-339">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="b0ef1-340">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="b0ef1-341">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="b0ef1-342">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b0ef1-343">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-343">What's new</span></span>

- <span data-ttu-id="b0ef1-344">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="b0ef1-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="b0ef1-345">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="b0ef1-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="b0ef1-346">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="b0ef1-347">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="b0ef1-348">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="b0ef1-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b0ef1-349">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-349">Known Issues</span></span>

<span data-ttu-id="b0ef1-350">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="b0ef1-351">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="b0ef1-352">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-352">This update is:</span></span>
> - <span data-ttu-id="b0ef1-353">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="b0ef1-354">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="b0ef1-355">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="b0ef1-356">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="b0ef1-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="b0ef1-357">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b0ef1-358">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="b0ef1-359">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="b0ef1-360">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="b0ef1-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="b0ef1-361">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="b0ef1-362">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="b0ef1-363">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="b0ef1-364">新機能</span><span class="sxs-lookup"><span data-stu-id="b0ef1-364">What's new</span></span>

- <span data-ttu-id="b0ef1-365">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="b0ef1-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="b0ef1-366">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="b0ef1-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="b0ef1-367">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="b0ef1-368">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b0ef1-369">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b0ef1-369">Known Issues</span></span>
<span data-ttu-id="b0ef1-370">この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="b0ef1-371">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="b0ef1-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="b0ef1-372">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="b0ef1-373">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="b0ef1-374">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="b0ef1-375">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="b0ef1-376">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="b0ef1-377">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="b0ef1-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="b0ef1-378">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="b0ef1-379">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="b0ef1-380">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="b0ef1-381">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="b0ef1-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="b0ef1-382">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="b0ef1-383">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="b0ef1-383">Windows 10 release</span></span>  |<span data-ttu-id="b0ef1-384">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="b0ef1-384">Platform version</span></span>  |<span data-ttu-id="b0ef1-385">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="b0ef1-385">Engine version</span></span> |<span data-ttu-id="b0ef1-386">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="b0ef1-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b0ef1-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="b0ef1-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="b0ef1-388">4.18.1909.6</span></span> |<span data-ttu-id="b0ef1-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="b0ef1-389">1.1.17000.2</span></span> | <span data-ttu-id="b0ef1-390">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-391">1909  (19H2)</span></span> |<span data-ttu-id="b0ef1-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b0ef1-392">4.18.1902.5</span></span> |<span data-ttu-id="b0ef1-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="b0ef1-393">1.1.16700.3</span></span> | <span data-ttu-id="b0ef1-394">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-395">1903  (19H1)</span></span> |<span data-ttu-id="b0ef1-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b0ef1-396">4.18.1902.5</span></span> |<span data-ttu-id="b0ef1-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="b0ef1-397">1.1.15600.4</span></span> | <span data-ttu-id="b0ef1-398">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-399">1809  (RS5)</span></span> |<span data-ttu-id="b0ef1-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="b0ef1-400">4.18.1807.18075</span></span> |<span data-ttu-id="b0ef1-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="b0ef1-401">1.1.15000.2</span></span> | <span data-ttu-id="b0ef1-402">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-403">1803  (RS4)</span></span> |<span data-ttu-id="b0ef1-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="b0ef1-404">4.13.17134.1</span></span> |<span data-ttu-id="b0ef1-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="b0ef1-405">1.1.14600.4</span></span> | <span data-ttu-id="b0ef1-406">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-407">1709  (RS3)</span></span> |<span data-ttu-id="b0ef1-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="b0ef1-408">4.12.16299.15</span></span> |<span data-ttu-id="b0ef1-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="b0ef1-409">1.1.14104.0</span></span> | <span data-ttu-id="b0ef1-410">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-411">1703  (RS2)</span></span> |<span data-ttu-id="b0ef1-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="b0ef1-412">4.11.15603.2</span></span> |<span data-ttu-id="b0ef1-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="b0ef1-413">1.1.13504.0</span></span> | <span data-ttu-id="b0ef1-414">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b0ef1-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-415">1607 (RS1)</span></span> |<span data-ttu-id="b0ef1-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="b0ef1-416">4.10.14393.3683</span></span> |<span data-ttu-id="b0ef1-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="b0ef1-417">1.1.12805.0</span></span> | <span data-ttu-id="b0ef1-418">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b0ef1-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="b0ef1-419">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="b0ef1-420">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="b0ef1-421">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="b0ef1-422">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="b0ef1-423">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="b0ef1-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="b0ef1-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="b0ef1-425">&ensp;パッケージ のバージョン: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="b0ef1-426">&ensp;プラットフォーム のバージョン: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="b0ef1-427">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b0ef1-428">&ensp;署名バージョン: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-429">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-429">Fixes</span></span>
- <span data-ttu-id="b0ef1-430">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-431">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-431">Additional information</span></span>
- <span data-ttu-id="b0ef1-432">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="b0ef1-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="b0ef1-434">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="b0ef1-435">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="b0ef1-436">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b0ef1-437">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-438">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-438">Fixes</span></span>
- <span data-ttu-id="b0ef1-439">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-440">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-440">Additional information</span></span>
- <span data-ttu-id="b0ef1-441">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="b0ef1-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="b0ef1-443">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="b0ef1-444">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="b0ef1-445">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="b0ef1-446">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-447">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-447">Fixes</span></span>
- <span data-ttu-id="b0ef1-448">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-449">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-449">Additional information</span></span>
- <span data-ttu-id="b0ef1-450">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="b0ef1-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="b0ef1-452">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="b0ef1-453">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="b0ef1-454">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b0ef1-455">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-456">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-456">Fixes</span></span>
- <span data-ttu-id="b0ef1-457">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-458">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-458">Additional information</span></span>
- <span data-ttu-id="b0ef1-459">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="b0ef1-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="b0ef1-461">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="b0ef1-462">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b0ef1-463">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b0ef1-464">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-465">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-465">Fixes</span></span>
- <span data-ttu-id="b0ef1-466">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-467">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-467">Additional information</span></span>
- <span data-ttu-id="b0ef1-468">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="b0ef1-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="b0ef1-470">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="b0ef1-471">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b0ef1-472">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="b0ef1-473">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-474">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-474">Fixes</span></span>
- <span data-ttu-id="b0ef1-475">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-476">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-476">Additional information</span></span>
- <span data-ttu-id="b0ef1-477">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="b0ef1-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="b0ef1-479">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="b0ef1-480">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b0ef1-481">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b0ef1-482">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-483">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-483">Fixes</span></span>
- <span data-ttu-id="b0ef1-484">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-485">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-485">Additional information</span></span>
- <span data-ttu-id="b0ef1-486">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="b0ef1-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="b0ef1-488">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="b0ef1-489">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b0ef1-490">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b0ef1-491">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-492">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-492">Fixes</span></span>
- <span data-ttu-id="b0ef1-493">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-494">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-494">Additional information</span></span>
- <span data-ttu-id="b0ef1-495">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="b0ef1-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="b0ef1-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="b0ef1-497">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b0ef1-498">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="b0ef1-499">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b0ef1-500">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-501">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-501">Fixes</span></span>
- <span data-ttu-id="b0ef1-502">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-503">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-503">Additional information</span></span>
- <span data-ttu-id="b0ef1-504">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b0ef1-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="b0ef1-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="b0ef1-506">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b0ef1-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b0ef1-507">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="b0ef1-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="b0ef1-508">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="b0ef1-509">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="b0ef1-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b0ef1-510">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-510">Fixes</span></span>
- <span data-ttu-id="b0ef1-511">なし</span><span class="sxs-lookup"><span data-stu-id="b0ef1-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b0ef1-512">追加情報</span><span class="sxs-lookup"><span data-stu-id="b0ef1-512">Additional information</span></span>
- <span data-ttu-id="b0ef1-513">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="b0ef1-514">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="b0ef1-514">Additional resources</span></span>

| <span data-ttu-id="b0ef1-515">記事</span><span class="sxs-lookup"><span data-stu-id="b0ef1-515">Article</span></span> | <span data-ttu-id="b0ef1-516">説明</span><span class="sxs-lookup"><span data-stu-id="b0ef1-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="b0ef1-517">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b0ef1-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="b0ef1-518">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="b0ef1-519">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="b0ef1-520">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b0ef1-521">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="b0ef1-522">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="b0ef1-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="b0ef1-523">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="b0ef1-524">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="b0ef1-525">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="b0ef1-526">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b0ef1-527">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="b0ef1-528">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b0ef1-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="b0ef1-529">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0ef1-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
