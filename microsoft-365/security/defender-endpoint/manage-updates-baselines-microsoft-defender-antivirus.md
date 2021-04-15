---
title: Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する
description: Microsoft Defender Antivirus が保護と製品の更新プログラムを受け取る方法を管理します。
keywords: 更新プログラム、セキュリティ 基準、保護、更新のスケジュール、強制的な更新、モバイル更新、wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b70cf96cde7d4dff8e2a4db6ce2469090dba7eb1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765613"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="8d658-104">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="8d658-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="8d658-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8d658-105">**Applies to:**</span></span>

- [<span data-ttu-id="8d658-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8d658-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="8d658-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="8d658-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="8d658-108">Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="8d658-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="8d658-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-109">Security intelligence updates</span></span>
- <span data-ttu-id="8d658-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="8d658-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d658-111">Microsoft Defender ウイルス対策を最新の状態に保つことは、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="8d658-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="8d658-112">Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、ウイルス対策保護を [更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="8d658-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="8d658-113">最新のエンジン、プラットフォーム、署名の日付を確認するには、Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="8d658-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="8d658-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-114">Security intelligence updates</span></span>

<span data-ttu-id="8d658-115">Microsoft Defender Antivirus は、 [クラウド](cloud-protection-microsoft-defender-antivirus.md) 配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d658-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="8d658-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="8d658-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="8d658-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="8d658-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="8d658-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="8d658-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="8d658-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d658-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="8d658-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="8d658-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="8d658-121">詳細については [、「Use Microsoft cloud-provided protection in Microsoft Defender Antivirus」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="8d658-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="8d658-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム」 [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="8d658-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="8d658-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="8d658-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="8d658-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="8d658-124">Product updates</span></span>

<span data-ttu-id="8d658-125">Microsoft Defender ウイルス対策では、月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、Windows 10 リリースと共に主要な機能更新プログラムを受け取る予定です。 </span><span class="sxs-lookup"><span data-stu-id="8d658-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="8d658-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="8d658-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="8d658-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="8d658-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="8d658-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8d658-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="8d658-129">ネットワーク内のエンドポイントに Microsoft および Windows の更新プログラムを展開するために使用する通常の方法。</span><span class="sxs-lookup"><span data-stu-id="8d658-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="8d658-130">詳細については [、「Microsoft Defender ウイルス対策保護更新プログラムのソースを管理する」を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="8d658-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="8d658-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="8d658-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="8d658-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="8d658-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="8d658-133">プラットフォーム更新プログラムを更新またはインストールする方法については [、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="8d658-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="8d658-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="8d658-134">All our updates contain</span></span> 
- <span data-ttu-id="8d658-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="8d658-135">performance improvements;</span></span>
- <span data-ttu-id="8d658-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="8d658-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="8d658-137">統合の改善 (クラウド、Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="8d658-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="8d658-138">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="8d658-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="8d658-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="8d658-140">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="8d658-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="8d658-141">&ensp;プラットフォーム: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="8d658-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="8d658-142">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="8d658-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="8d658-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-144">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-144">What's new</span></span>

- <span data-ttu-id="8d658-145">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="8d658-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="8d658-146">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="8d658-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="8d658-147">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d658-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-148">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-148">Known Issues</span></span>
<span data-ttu-id="8d658-149">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8d658-150">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="8d658-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="8d658-151">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="8d658-152">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="8d658-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="8d658-153">&ensp;プラットフォーム: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="8d658-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="8d658-154">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="8d658-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="8d658-155">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="8d658-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-156">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-156">What's new</span></span>

- <span data-ttu-id="8d658-157">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="8d658-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="8d658-158">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="8d658-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-159">Known Issues</span></span>
<span data-ttu-id="8d658-160">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8d658-161">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="8d658-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="8d658-162">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="8d658-163">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="8d658-164">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="8d658-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="8d658-165">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="8d658-166">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="8d658-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-167">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-167">What's new</span></span>

- <span data-ttu-id="8d658-168">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="8d658-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="8d658-169">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="8d658-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="8d658-170">Microsoft Defender ウイルス対策サービスのスパム対策機能の改善点</span><span class="sxs-lookup"><span data-stu-id="8d658-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="8d658-171">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="8d658-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="8d658-172">修正: EDR ブロック通知は、リアルタイム保護が初期検出を実行した後も脅威の履歴に残ります</span><span class="sxs-lookup"><span data-stu-id="8d658-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-173">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-173">Known Issues</span></span>
<span data-ttu-id="8d658-174">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="8d658-175">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="8d658-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="8d658-176">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="8d658-177">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="8d658-178">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="8d658-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="8d658-179">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="8d658-180">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="8d658-181">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="8d658-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="8d658-182">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="8d658-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="8d658-183">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="8d658-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-184">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-184">What's new</span></span>

- <span data-ttu-id="8d658-185">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="8d658-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-186">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-186">Known Issues</span></span>
<span data-ttu-id="8d658-187">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8d658-188">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="8d658-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="8d658-189">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="8d658-190">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="8d658-191">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="8d658-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="8d658-192">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="8d658-193">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="8d658-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-194">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-194">What's new</span></span>

- <span data-ttu-id="8d658-195">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="8d658-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="8d658-196">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="8d658-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="8d658-197">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="8d658-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="8d658-198">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="8d658-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-199">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-199">Known Issues</span></span>

<span data-ttu-id="8d658-200">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8d658-201">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="8d658-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="8d658-202">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="8d658-203">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="8d658-204">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="8d658-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="8d658-205">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="8d658-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="8d658-206">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-207">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-207">What's new</span></span>

- <span data-ttu-id="8d658-208">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="8d658-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="8d658-209">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="8d658-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="8d658-210">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="8d658-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="8d658-211">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d658-211">New management interfaces for:</span></span>
   - <span data-ttu-id="8d658-212">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="8d658-212">UDP Inspection</span></span>
   - <span data-ttu-id="8d658-213">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="8d658-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="8d658-214">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="8d658-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="8d658-215">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="8d658-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="8d658-216">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="8d658-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-217">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-217">Known Issues</span></span>

<span data-ttu-id="8d658-218">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="8d658-219">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="8d658-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="8d658-220">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="8d658-221">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="8d658-222">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="8d658-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="8d658-223">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="8d658-224">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="8d658-225">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-225">What's new</span></span>

- <span data-ttu-id="8d658-226">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="8d658-226">Add more telemetry events</span></span>
- <span data-ttu-id="8d658-227">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="8d658-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="8d658-228">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="8d658-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="8d658-229">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="8d658-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="8d658-230">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="8d658-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="8d658-231">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="8d658-232">Microsoft Defender ウイルス対策は、別のウイルス対策プログラムを検出すると自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="8d658-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="8d658-233">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-233">Known Issues</span></span>
<span data-ttu-id="8d658-234">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-235">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="8d658-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="8d658-236">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="8d658-237">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="8d658-238">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="8d658-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="8d658-239">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="8d658-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="8d658-240">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-241">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-241">What's new</span></span>

- <span data-ttu-id="8d658-242">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="8d658-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="8d658-243">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="8d658-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-244">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-244">Known Issues</span></span>
<span data-ttu-id="8d658-245">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-246">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="8d658-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="8d658-247">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="8d658-248">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="8d658-249">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="8d658-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="8d658-250">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="8d658-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="8d658-251">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-252">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-252">What's new</span></span>

- <span data-ttu-id="8d658-253">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="8d658-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="8d658-254">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="8d658-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="8d658-255">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="8d658-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="8d658-256">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="8d658-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="8d658-257">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="8d658-257">Fixed registry query</span></span> 
- <span data-ttu-id="8d658-258">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="8d658-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-259">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-259">Known Issues</span></span>
<span data-ttu-id="8d658-260">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-261">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="8d658-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="8d658-262">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="8d658-263">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="8d658-264">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="8d658-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="8d658-265">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="8d658-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="8d658-266">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-267">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-267">What's new</span></span>

- <span data-ttu-id="8d658-268">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="8d658-268">Improved logging for scan events</span></span>
- <span data-ttu-id="8d658-269">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="8d658-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="8d658-270">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="8d658-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="8d658-271">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="8d658-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="8d658-272">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="8d658-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="8d658-273">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="8d658-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-274">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-274">Known Issues</span></span>
<span data-ttu-id="8d658-275">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-276">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="8d658-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="8d658-277">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="8d658-278">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="8d658-279">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="8d658-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="8d658-280">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="8d658-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="8d658-281">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-282">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-282">What's new</span></span>
- <span data-ttu-id="8d658-283">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="8d658-283">WDfilter improvements</span></span>
- <span data-ttu-id="8d658-284">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="8d658-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="8d658-285">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="8d658-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="8d658-286">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="8d658-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="8d658-287">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="8d658-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="8d658-288">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="8d658-288">UEFI scan capability</span></span>
- <span data-ttu-id="8d658-289">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="8d658-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="8d658-290">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-290">Known Issues</span></span>
<span data-ttu-id="8d658-291">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-292">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="8d658-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="8d658-293">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="8d658-294">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="8d658-295">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="8d658-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="8d658-296">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="8d658-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="8d658-297">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8d658-298">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-298">What's new</span></span>

- <span data-ttu-id="8d658-299">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8d658-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="8d658-300">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="8d658-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="8d658-301">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="8d658-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="8d658-302">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="8d658-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="8d658-303">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="8d658-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="8d658-304">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-304">Known Issues</span></span>
<span data-ttu-id="8d658-305">[**固定**]Microsoft Defender ウイルス対策は、スキャンを実行するときにファイルをスキップしています。</span><span class="sxs-lookup"><span data-stu-id="8d658-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="8d658-306">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="8d658-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="8d658-307">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="8d658-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="8d658-308">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="8d658-309">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="8d658-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="8d658-310">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="8d658-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="8d658-311">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="8d658-312">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="8d658-313">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-313">Known Issues</span></span>
<span data-ttu-id="8d658-314">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="8d658-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-315">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="8d658-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="8d658-316">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="8d658-317">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="8d658-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="8d658-318">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="8d658-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="8d658-319">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="8d658-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="8d658-320">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="8d658-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="8d658-321">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-321">What's new</span></span>

- <span data-ttu-id="8d658-322">Exchange を使用した WS2016 の固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="8d658-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="8d658-323">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="8d658-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="8d658-324">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="8d658-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="8d658-325">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="8d658-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="8d658-326">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="8d658-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="8d658-327">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-327">Known Issues</span></span>

<span data-ttu-id="8d658-328">[**固定**] 最新の [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d658-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="8d658-329">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="8d658-330">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="8d658-330">This update is:</span></span>
> - <span data-ttu-id="8d658-331">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="8d658-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="8d658-332">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="8d658-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="8d658-333">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="8d658-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="8d658-334">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="8d658-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="8d658-335">は Windows Update でのみ [提供されます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="8d658-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="8d658-336">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="8d658-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="8d658-337">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="8d658-338">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="8d658-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="8d658-339">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="8d658-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="8d658-340">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="8d658-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="8d658-341">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="8d658-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="8d658-342">新機能</span><span class="sxs-lookup"><span data-stu-id="8d658-342">What's new</span></span>

- <span data-ttu-id="8d658-343">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="8d658-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="8d658-344">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="8d658-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="8d658-345">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="8d658-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="8d658-346">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="8d658-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="8d658-347">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8d658-347">Known Issues</span></span>
<span data-ttu-id="8d658-348">この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d658-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="8d658-349">Microsoft Defender ウイルス対策プラットフォームのサポート</span><span class="sxs-lookup"><span data-stu-id="8d658-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="8d658-350">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="8d658-351">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d658-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="8d658-352">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="8d658-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="8d658-353">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="8d658-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="8d658-354">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="8d658-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="8d658-355">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="8d658-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="8d658-356">\* Windows 10 リリース バージョン (Windows [10](#platform-version-included-with-windows-10-releases)リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引き続きテクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="8d658-357">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="8d658-358">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d658-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="8d658-359">Windows 10 リリースに含まれるプラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="8d658-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="8d658-360">次の表に、最新の Windows 10 リリースに同梱されている Microsoft Defender ウイルス対策プラットフォームとエンジン のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="8d658-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="8d658-361">Windows 10 リリース</span><span class="sxs-lookup"><span data-stu-id="8d658-361">Windows 10 release</span></span>  |<span data-ttu-id="8d658-362">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="8d658-362">Platform version</span></span>  |<span data-ttu-id="8d658-363">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="8d658-363">Engine version</span></span> |<span data-ttu-id="8d658-364">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="8d658-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="8d658-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="8d658-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="8d658-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="8d658-366">4.18.1909.6</span></span> |<span data-ttu-id="8d658-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="8d658-367">1.1.17000.2</span></span> | <span data-ttu-id="8d658-368">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="8d658-369">1909  (19H2)</span></span> |<span data-ttu-id="8d658-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="8d658-370">4.18.1902.5</span></span> |<span data-ttu-id="8d658-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="8d658-371">1.1.16700.3</span></span> | <span data-ttu-id="8d658-372">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="8d658-373">1903  (19H1)</span></span> |<span data-ttu-id="8d658-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="8d658-374">4.18.1902.5</span></span> |<span data-ttu-id="8d658-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="8d658-375">1.1.15600.4</span></span> | <span data-ttu-id="8d658-376">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="8d658-377">1809  (RS5)</span></span> |<span data-ttu-id="8d658-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="8d658-378">4.18.1807.18075</span></span> |<span data-ttu-id="8d658-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="8d658-379">1.1.15000.2</span></span> | <span data-ttu-id="8d658-380">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="8d658-381">1803  (RS4)</span></span> |<span data-ttu-id="8d658-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="8d658-382">4.13.17134.1</span></span> |<span data-ttu-id="8d658-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="8d658-383">1.1.14600.4</span></span> | <span data-ttu-id="8d658-384">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="8d658-385">1709  (RS3)</span></span> |<span data-ttu-id="8d658-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="8d658-386">4.12.16299.15</span></span> |<span data-ttu-id="8d658-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="8d658-387">1.1.14104.0</span></span> | <span data-ttu-id="8d658-388">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="8d658-389">1703  (RS2)</span></span> |<span data-ttu-id="8d658-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="8d658-390">4.11.15603.2</span></span> |<span data-ttu-id="8d658-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="8d658-391">1.1.13504.0</span></span> | <span data-ttu-id="8d658-392">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8d658-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="8d658-393">1607 (RS1)</span></span> |<span data-ttu-id="8d658-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="8d658-394">4.10.14393.3683</span></span> |<span data-ttu-id="8d658-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="8d658-395">1.1.12805.0</span></span> | <span data-ttu-id="8d658-396">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="8d658-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="8d658-397">Windows 10 リリース情報については、「Windows ライフサイクル ファクト シート [」を参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="8d658-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="8d658-398">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="8d658-399">Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d658-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="8d658-400">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d658-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="8d658-401">詳細については、「Microsoft Defender update for Windows オペレーティング システム [インストール イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="8d658-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="8d658-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="8d658-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="8d658-403">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="8d658-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="8d658-404">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="8d658-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="8d658-405">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="8d658-406">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-407">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-407">Fixes</span></span>
- <span data-ttu-id="8d658-408">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-409">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-409">Additional information</span></span>
- <span data-ttu-id="8d658-410">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="8d658-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="8d658-412">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="8d658-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="8d658-413">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="8d658-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="8d658-414">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="8d658-415">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-416">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-416">Fixes</span></span>
- <span data-ttu-id="8d658-417">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-418">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-418">Additional information</span></span>
- <span data-ttu-id="8d658-419">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="8d658-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="8d658-421">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="8d658-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="8d658-422">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="8d658-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="8d658-423">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="8d658-424">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-425">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-425">Fixes</span></span>
- <span data-ttu-id="8d658-426">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-427">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-427">Additional information</span></span>
- <span data-ttu-id="8d658-428">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="8d658-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="8d658-430">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="8d658-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="8d658-431">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="8d658-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="8d658-432">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="8d658-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="8d658-433">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-434">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-434">Fixes</span></span>
- <span data-ttu-id="8d658-435">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-436">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-436">Additional information</span></span>
- <span data-ttu-id="8d658-437">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="8d658-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="8d658-439">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="8d658-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="8d658-440">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="8d658-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="8d658-441">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="8d658-442">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-443">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-443">Fixes</span></span>
- <span data-ttu-id="8d658-444">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-445">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-445">Additional information</span></span>
- <span data-ttu-id="8d658-446">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="8d658-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="8d658-448">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="8d658-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="8d658-449">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="8d658-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="8d658-450">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="8d658-451">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-452">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-452">Fixes</span></span>
- <span data-ttu-id="8d658-453">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-454">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-454">Additional information</span></span>
- <span data-ttu-id="8d658-455">Microsoft Defender ウイルス対策署名の更新</span><span class="sxs-lookup"><span data-stu-id="8d658-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="8d658-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="8d658-457">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="8d658-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="8d658-458">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="8d658-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="8d658-459">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="8d658-460">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-461">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-461">Fixes</span></span>
- <span data-ttu-id="8d658-462">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-463">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-463">Additional information</span></span>
- <span data-ttu-id="8d658-464">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8d658-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="8d658-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="8d658-466">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="8d658-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="8d658-467">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="8d658-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="8d658-468">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="8d658-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="8d658-469">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="8d658-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8d658-470">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-470">Fixes</span></span>
- <span data-ttu-id="8d658-471">なし</span><span class="sxs-lookup"><span data-stu-id="8d658-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8d658-472">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d658-472">Additional information</span></span>
- <span data-ttu-id="8d658-473">Windows 10 RS1 以降の OS インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8d658-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="8d658-474">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="8d658-474">Additional resources</span></span>

| <span data-ttu-id="8d658-475">記事</span><span class="sxs-lookup"><span data-stu-id="8d658-475">Article</span></span> | <span data-ttu-id="8d658-476">説明</span><span class="sxs-lookup"><span data-stu-id="8d658-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="8d658-477">Windows オペレーティング システムのインストール イメージ用の Microsoft Defender 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d658-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="8d658-478">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d658-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="8d658-479">Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 インストール イメージの Microsoft Defender ウイルス対策更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="8d658-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="8d658-480">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="8d658-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="8d658-481">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="8d658-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="8d658-482">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="8d658-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="8d658-483">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8d658-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="8d658-484">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="8d658-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="8d658-485">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d658-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="8d658-486">イベントベースの強制的な更新の管理</span><span class="sxs-lookup"><span data-stu-id="8d658-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="8d658-487">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="8d658-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="8d658-488">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="8d658-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="8d658-489">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8d658-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
