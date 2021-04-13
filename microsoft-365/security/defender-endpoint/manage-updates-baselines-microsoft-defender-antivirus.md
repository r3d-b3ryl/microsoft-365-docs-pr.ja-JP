---
title: Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する
description: Microsoft Defender Antivirus が保護と製品の更新プログラムを受け取る方法を管理します。
keywords: 更新プログラム、セキュリティ 基準、保護、更新のスケジュール、強制的な更新、モバイル更新、wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690981"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="bc88b-104">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="bc88b-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="bc88b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bc88b-105">**Applies to:**</span></span>

- [<span data-ttu-id="bc88b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bc88b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="bc88b-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="bc88b-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="bc88b-108">Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="bc88b-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-109">Security intelligence updates</span></span>
- <span data-ttu-id="bc88b-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="bc88b-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc88b-111">Microsoft Defender ウイルス対策を最新の状態に保つことは、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="bc88b-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="bc88b-112">Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、ウイルス対策保護を [更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="bc88b-113">最新のエンジン、プラットフォーム、署名の日付を確認するには、Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="bc88b-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-114">Security intelligence updates</span></span>

<span data-ttu-id="bc88b-115">Microsoft Defender Antivirus は、 [クラウド](cloud-protection-microsoft-defender-antivirus.md) 配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc88b-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="bc88b-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="bc88b-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="bc88b-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="bc88b-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="bc88b-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="bc88b-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="bc88b-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="bc88b-121">詳細については [、「Use Microsoft cloud-provided protection in Microsoft Defender Antivirus」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="bc88b-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム」 [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="bc88b-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="bc88b-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="bc88b-124">Product updates</span></span>

<span data-ttu-id="bc88b-125">Microsoft Defender ウイルス対策では、月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、Windows 10 リリースと共に主要な機能更新プログラムを受け取る予定です。 </span><span class="sxs-lookup"><span data-stu-id="bc88b-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="bc88b-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="bc88b-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="bc88b-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="bc88b-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc88b-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="bc88b-129">ネットワーク内のエンドポイントに Microsoft および Windows の更新プログラムを展開するために使用する通常の方法。</span><span class="sxs-lookup"><span data-stu-id="bc88b-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="bc88b-130">詳細については [、「Microsoft Defender ウイルス対策保護更新プログラムのソースを管理する」を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="bc88b-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="bc88b-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="bc88b-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="bc88b-133">プラットフォーム更新プログラムを更新またはインストールする方法については [、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="bc88b-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="bc88b-134">All our updates contain</span></span> 
- <span data-ttu-id="bc88b-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="bc88b-135">performance improvements;</span></span>
- <span data-ttu-id="bc88b-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="bc88b-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="bc88b-137">統合の改善 (クラウド、Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="bc88b-138">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="bc88b-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="bc88b-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="bc88b-140">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="bc88b-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="bc88b-141">&ensp;プラットフォーム: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="bc88b-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="bc88b-142">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="bc88b-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="bc88b-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-144">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-144">What's new</span></span>

- <span data-ttu-id="bc88b-145">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="bc88b-146">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="bc88b-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="bc88b-147">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="bc88b-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-148">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-148">Known Issues</span></span>
<span data-ttu-id="bc88b-149">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="bc88b-150">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="bc88b-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="bc88b-151">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="bc88b-152">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="bc88b-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="bc88b-153">&ensp;プラットフォーム: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="bc88b-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="bc88b-154">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="bc88b-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="bc88b-155">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="bc88b-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-156">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-156">What's new</span></span>

- <span data-ttu-id="bc88b-157">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="bc88b-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="bc88b-158">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="bc88b-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-159">Known Issues</span></span>
<span data-ttu-id="bc88b-160">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="bc88b-161">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="bc88b-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="bc88b-162">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="bc88b-163">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="bc88b-164">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="bc88b-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="bc88b-165">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="bc88b-166">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="bc88b-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-167">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-167">What's new</span></span>

- <span data-ttu-id="bc88b-168">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="bc88b-169">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="bc88b-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="bc88b-170">Microsoft Defender ウイルス対策サービスのスパム対策機能の改善点</span><span class="sxs-lookup"><span data-stu-id="bc88b-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="bc88b-171">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="bc88b-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="bc88b-172">修正: EDR ブロック通知は、リアルタイム保護が初期検出を実行した後も脅威の履歴に残ります</span><span class="sxs-lookup"><span data-stu-id="bc88b-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-173">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-173">Known Issues</span></span>
<span data-ttu-id="bc88b-174">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="bc88b-175">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="bc88b-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="bc88b-176">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="bc88b-177">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="bc88b-178">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="bc88b-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="bc88b-179">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="bc88b-180">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="bc88b-181">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="bc88b-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="bc88b-182">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="bc88b-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="bc88b-183">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="bc88b-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-184">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-184">What's new</span></span>

- <span data-ttu-id="bc88b-185">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-186">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-186">Known Issues</span></span>
<span data-ttu-id="bc88b-187">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="bc88b-188">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="bc88b-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="bc88b-189">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="bc88b-190">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="bc88b-191">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="bc88b-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="bc88b-192">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="bc88b-193">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="bc88b-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-194">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-194">What's new</span></span>

- <span data-ttu-id="bc88b-195">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="bc88b-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="bc88b-196">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="bc88b-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="bc88b-197">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="bc88b-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="bc88b-198">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="bc88b-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-199">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-199">Known Issues</span></span>

<span data-ttu-id="bc88b-200">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="bc88b-201">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="bc88b-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="bc88b-202">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="bc88b-203">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="bc88b-204">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="bc88b-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="bc88b-205">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="bc88b-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="bc88b-206">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-207">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-207">What's new</span></span>

- <span data-ttu-id="bc88b-208">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="bc88b-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="bc88b-209">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="bc88b-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="bc88b-210">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="bc88b-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="bc88b-211">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc88b-211">New management interfaces for:</span></span>
   - <span data-ttu-id="bc88b-212">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="bc88b-212">UDP Inspection</span></span>
   - <span data-ttu-id="bc88b-213">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="bc88b-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="bc88b-214">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="bc88b-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="bc88b-215">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="bc88b-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="bc88b-216">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-217">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-217">Known Issues</span></span>

<span data-ttu-id="bc88b-218">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="bc88b-219">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="bc88b-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="bc88b-220">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="bc88b-221">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="bc88b-222">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="bc88b-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="bc88b-223">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="bc88b-224">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="bc88b-225">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-225">What's new</span></span>

- <span data-ttu-id="bc88b-226">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="bc88b-226">Add more telemetry events</span></span>
- <span data-ttu-id="bc88b-227">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="bc88b-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="bc88b-228">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="bc88b-229">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="bc88b-230">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="bc88b-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="bc88b-231">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="bc88b-232">Microsoft Defender ウイルス対策は、別のウイルス対策プログラムを検出すると自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="bc88b-233">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-233">Known Issues</span></span>
<span data-ttu-id="bc88b-234">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-235">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="bc88b-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="bc88b-236">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="bc88b-237">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="bc88b-238">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="bc88b-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="bc88b-239">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="bc88b-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="bc88b-240">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-241">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-241">What's new</span></span>

- <span data-ttu-id="bc88b-242">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="bc88b-243">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-244">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-244">Known Issues</span></span>
<span data-ttu-id="bc88b-245">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-246">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="bc88b-247">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="bc88b-248">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="bc88b-249">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="bc88b-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="bc88b-250">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="bc88b-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="bc88b-251">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-252">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-252">What's new</span></span>

- <span data-ttu-id="bc88b-253">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="bc88b-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="bc88b-254">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="bc88b-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="bc88b-255">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="bc88b-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="bc88b-256">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="bc88b-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="bc88b-257">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="bc88b-257">Fixed registry query</span></span> 
- <span data-ttu-id="bc88b-258">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="bc88b-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-259">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-259">Known Issues</span></span>
<span data-ttu-id="bc88b-260">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-261">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="bc88b-262">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="bc88b-263">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="bc88b-264">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="bc88b-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="bc88b-265">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="bc88b-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="bc88b-266">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-267">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-267">What's new</span></span>

- <span data-ttu-id="bc88b-268">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="bc88b-268">Improved logging for scan events</span></span>
- <span data-ttu-id="bc88b-269">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="bc88b-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="bc88b-270">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="bc88b-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="bc88b-271">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="bc88b-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="bc88b-272">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="bc88b-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="bc88b-273">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="bc88b-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-274">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-274">Known Issues</span></span>
<span data-ttu-id="bc88b-275">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-276">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="bc88b-277">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="bc88b-278">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="bc88b-279">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="bc88b-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="bc88b-280">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="bc88b-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="bc88b-281">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-282">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-282">What's new</span></span>
- <span data-ttu-id="bc88b-283">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="bc88b-283">WDfilter improvements</span></span>
- <span data-ttu-id="bc88b-284">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="bc88b-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="bc88b-285">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="bc88b-286">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="bc88b-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="bc88b-287">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="bc88b-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="bc88b-288">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-288">UEFI scan capability</span></span>
- <span data-ttu-id="bc88b-289">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="bc88b-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="bc88b-290">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-290">Known Issues</span></span>
<span data-ttu-id="bc88b-291">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-292">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="bc88b-293">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="bc88b-294">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="bc88b-295">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="bc88b-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="bc88b-296">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="bc88b-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="bc88b-297">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="bc88b-298">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-298">What's new</span></span>

- <span data-ttu-id="bc88b-299">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="bc88b-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="bc88b-300">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="bc88b-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="bc88b-301">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="bc88b-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="bc88b-302">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="bc88b-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="bc88b-303">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="bc88b-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="bc88b-304">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-304">Known Issues</span></span>
<span data-ttu-id="bc88b-305">[**固定**]Microsoft Defender ウイルス対策は、スキャンを実行するときにファイルをスキップしています。</span><span class="sxs-lookup"><span data-stu-id="bc88b-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="bc88b-306">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="bc88b-307">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="bc88b-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="bc88b-308">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="bc88b-309">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="bc88b-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="bc88b-310">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="bc88b-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="bc88b-311">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="bc88b-312">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="bc88b-313">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-313">Known Issues</span></span>
<span data-ttu-id="bc88b-314">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="bc88b-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-315">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="bc88b-316">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="bc88b-317">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="bc88b-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="bc88b-318">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="bc88b-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="bc88b-319">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="bc88b-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="bc88b-320">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="bc88b-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="bc88b-321">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-321">What's new</span></span>

- <span data-ttu-id="bc88b-322">Exchange を使用した WS2016 の固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="bc88b-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="bc88b-323">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="bc88b-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="bc88b-324">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="bc88b-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="bc88b-325">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="bc88b-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="bc88b-326">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="bc88b-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="bc88b-327">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-327">Known Issues</span></span>

<span data-ttu-id="bc88b-328">[**固定**] 最新の [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="bc88b-329">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="bc88b-330">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="bc88b-330">This update is:</span></span>
> - <span data-ttu-id="bc88b-331">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="bc88b-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="bc88b-332">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="bc88b-333">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="bc88b-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="bc88b-334">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="bc88b-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="bc88b-335">は Windows Update でのみ [提供されます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="bc88b-336">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="bc88b-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="bc88b-337">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="bc88b-338">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="bc88b-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="bc88b-339">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="bc88b-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="bc88b-340">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="bc88b-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="bc88b-341">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="bc88b-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="bc88b-342">新機能</span><span class="sxs-lookup"><span data-stu-id="bc88b-342">What's new</span></span>

- <span data-ttu-id="bc88b-343">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="bc88b-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="bc88b-344">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="bc88b-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="bc88b-345">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="bc88b-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="bc88b-346">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="bc88b-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="bc88b-347">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bc88b-347">Known Issues</span></span>
<span data-ttu-id="bc88b-348">この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="bc88b-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="bc88b-349">Microsoft Defender ウイルス対策プラットフォームのサポート</span><span class="sxs-lookup"><span data-stu-id="bc88b-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="bc88b-350">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="bc88b-351">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="bc88b-352">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="bc88b-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="bc88b-353">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="bc88b-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="bc88b-354">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="bc88b-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="bc88b-355">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="bc88b-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="bc88b-356">\* Windows 10 リリース バージョン (Windows [10](#platform-version-included-with-windows-10-releases)リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引き続きテクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="bc88b-357">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="bc88b-358">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="bc88b-359">Windows 10 リリースに含まれるプラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="bc88b-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="bc88b-360">次の表に、最新の Windows 10 リリースに同梱されている Microsoft Defender ウイルス対策プラットフォームとエンジン のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="bc88b-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="bc88b-361">Windows 10 リリース</span><span class="sxs-lookup"><span data-stu-id="bc88b-361">Windows 10 release</span></span>  |<span data-ttu-id="bc88b-362">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="bc88b-362">Platform version</span></span>  |<span data-ttu-id="bc88b-363">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="bc88b-363">Engine version</span></span> |<span data-ttu-id="bc88b-364">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="bc88b-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="bc88b-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="bc88b-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="bc88b-366">4.18.1909.6</span></span> |<span data-ttu-id="bc88b-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="bc88b-367">1.1.17000.2</span></span> | <span data-ttu-id="bc88b-368">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-369">1909  (19H2)</span></span> |<span data-ttu-id="bc88b-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="bc88b-370">4.18.1902.5</span></span> |<span data-ttu-id="bc88b-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="bc88b-371">1.1.16700.3</span></span> | <span data-ttu-id="bc88b-372">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="bc88b-373">1903  (19H1)</span></span> |<span data-ttu-id="bc88b-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="bc88b-374">4.18.1902.5</span></span> |<span data-ttu-id="bc88b-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="bc88b-375">1.1.15600.4</span></span> | <span data-ttu-id="bc88b-376">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="bc88b-377">1809  (RS5)</span></span> |<span data-ttu-id="bc88b-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="bc88b-378">4.18.1807.18075</span></span> |<span data-ttu-id="bc88b-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="bc88b-379">1.1.15000.2</span></span> | <span data-ttu-id="bc88b-380">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="bc88b-381">1803  (RS4)</span></span> |<span data-ttu-id="bc88b-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="bc88b-382">4.13.17134.1</span></span> |<span data-ttu-id="bc88b-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="bc88b-383">1.1.14600.4</span></span> | <span data-ttu-id="bc88b-384">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="bc88b-385">1709  (RS3)</span></span> |<span data-ttu-id="bc88b-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="bc88b-386">4.12.16299.15</span></span> |<span data-ttu-id="bc88b-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="bc88b-387">1.1.14104.0</span></span> | <span data-ttu-id="bc88b-388">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="bc88b-389">1703  (RS2)</span></span> |<span data-ttu-id="bc88b-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="bc88b-390">4.11.15603.2</span></span> |<span data-ttu-id="bc88b-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="bc88b-391">1.1.13504.0</span></span> | <span data-ttu-id="bc88b-392">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="bc88b-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="bc88b-393">1607 (RS1)</span></span> |<span data-ttu-id="bc88b-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="bc88b-394">4.10.14393.3683</span></span> |<span data-ttu-id="bc88b-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="bc88b-395">1.1.12805.0</span></span> | <span data-ttu-id="bc88b-396">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="bc88b-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="bc88b-397">Windows 10 リリース情報については、「Windows ライフサイクル ファクト シート [」を参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="bc88b-398">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="bc88b-399">Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc88b-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="bc88b-400">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="bc88b-401">詳細については、「Microsoft Defender update for Windows オペレーティング システム [インストール イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="bc88b-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="bc88b-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="bc88b-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="bc88b-403">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="bc88b-404">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="bc88b-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="bc88b-405">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="bc88b-406">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-407">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-407">Fixes</span></span>
- <span data-ttu-id="bc88b-408">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-409">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-409">Additional information</span></span>
- <span data-ttu-id="bc88b-410">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="bc88b-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="bc88b-412">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="bc88b-413">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="bc88b-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="bc88b-414">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="bc88b-415">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-416">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-416">Fixes</span></span>
- <span data-ttu-id="bc88b-417">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-418">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-418">Additional information</span></span>
- <span data-ttu-id="bc88b-419">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="bc88b-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="bc88b-421">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="bc88b-422">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="bc88b-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="bc88b-423">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="bc88b-424">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-425">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-425">Fixes</span></span>
- <span data-ttu-id="bc88b-426">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-427">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-427">Additional information</span></span>
- <span data-ttu-id="bc88b-428">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="bc88b-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="bc88b-430">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="bc88b-431">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="bc88b-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="bc88b-432">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="bc88b-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="bc88b-433">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-434">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-434">Fixes</span></span>
- <span data-ttu-id="bc88b-435">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-436">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-436">Additional information</span></span>
- <span data-ttu-id="bc88b-437">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="bc88b-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="bc88b-439">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="bc88b-440">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="bc88b-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="bc88b-441">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="bc88b-442">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-443">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-443">Fixes</span></span>
- <span data-ttu-id="bc88b-444">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-445">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-445">Additional information</span></span>
- <span data-ttu-id="bc88b-446">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="bc88b-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="bc88b-448">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="bc88b-449">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="bc88b-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="bc88b-450">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="bc88b-451">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-452">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-452">Fixes</span></span>
- <span data-ttu-id="bc88b-453">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-454">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-454">Additional information</span></span>
- <span data-ttu-id="bc88b-455">Microsoft Defender ウイルス対策署名の更新</span><span class="sxs-lookup"><span data-stu-id="bc88b-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="bc88b-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="bc88b-457">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="bc88b-458">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="bc88b-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="bc88b-459">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="bc88b-460">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-461">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-461">Fixes</span></span>
- <span data-ttu-id="bc88b-462">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-463">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-463">Additional information</span></span>
- <span data-ttu-id="bc88b-464">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="bc88b-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="bc88b-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="bc88b-466">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="bc88b-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="bc88b-467">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="bc88b-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="bc88b-468">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="bc88b-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="bc88b-469">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="bc88b-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="bc88b-470">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-470">Fixes</span></span>
- <span data-ttu-id="bc88b-471">なし</span><span class="sxs-lookup"><span data-stu-id="bc88b-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="bc88b-472">追加情報</span><span class="sxs-lookup"><span data-stu-id="bc88b-472">Additional information</span></span>
- <span data-ttu-id="bc88b-473">Windows 10 RS1 以降の OS インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="bc88b-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="bc88b-474">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="bc88b-474">Additional resources</span></span>

| <span data-ttu-id="bc88b-475">記事</span><span class="sxs-lookup"><span data-stu-id="bc88b-475">Article</span></span> | <span data-ttu-id="bc88b-476">説明</span><span class="sxs-lookup"><span data-stu-id="bc88b-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="bc88b-477">Windows オペレーティング システムのインストール イメージ用の Microsoft Defender 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bc88b-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="bc88b-478">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc88b-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="bc88b-479">Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 インストール イメージの Microsoft Defender ウイルス対策更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc88b-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="bc88b-480">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="bc88b-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="bc88b-481">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="bc88b-482">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="bc88b-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="bc88b-483">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="bc88b-484">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="bc88b-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="bc88b-485">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="bc88b-486">イベントベースの強制的な更新の管理</span><span class="sxs-lookup"><span data-stu-id="bc88b-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="bc88b-487">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="bc88b-488">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="bc88b-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="bc88b-489">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc88b-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
