---
title: Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する
description: Microsoft Defender Antivirus が保護と製品の更新プログラムを受け取る方法を管理します。
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
ms.date: 05/06/2021
ms.openlocfilehash: 22a173d39c3ab8d1afd91a33b05e02e58da24aaa
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274558"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="e3713-104">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="e3713-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="e3713-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e3713-105">**Applies to:**</span></span>

- [<span data-ttu-id="e3713-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e3713-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="e3713-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="e3713-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="e3713-108">Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="e3713-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="e3713-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-109">Security intelligence updates</span></span>
- <span data-ttu-id="e3713-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="e3713-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3713-111">Microsoft Defender ウイルス対策を最新の状態に保つことは、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="e3713-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="e3713-112">Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、ウイルス対策保護を [更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="e3713-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="e3713-113">最新のエンジン、プラットフォーム、署名の日付を確認するには、Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="e3713-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="e3713-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-114">Security intelligence updates</span></span>

<span data-ttu-id="e3713-115">Microsoft Defender Antivirus は、 [クラウド](cloud-protection-microsoft-defender-antivirus.md) 配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3713-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="e3713-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="e3713-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="e3713-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="e3713-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="e3713-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="e3713-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="e3713-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3713-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="e3713-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="e3713-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="e3713-121">詳細については [、「Use Microsoft cloud-provided protection in Microsoft Defender Antivirus」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e3713-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="e3713-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム」 [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="e3713-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="e3713-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="e3713-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="e3713-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="e3713-124">Product updates</span></span>

<span data-ttu-id="e3713-125">Microsoft Defender ウイルス対策では、月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、Windows 10 リリースと共に主要な機能更新プログラムを受け取る予定です。 </span><span class="sxs-lookup"><span data-stu-id="e3713-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="e3713-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="e3713-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="e3713-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="e3713-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="e3713-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e3713-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="e3713-129">ネットワーク内のエンドポイントに Microsoft および Windows の更新プログラムを展開するために使用する通常の方法。</span><span class="sxs-lookup"><span data-stu-id="e3713-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="e3713-130">詳細については [、「Microsoft Defender ウイルス対策保護更新プログラムのソースを管理する」を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="e3713-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="e3713-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="e3713-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="e3713-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="e3713-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="e3713-133">プラットフォーム更新プログラムを更新またはインストールする方法については [、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="e3713-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="e3713-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="e3713-134">All our updates contain</span></span> 
- <span data-ttu-id="e3713-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="e3713-135">performance improvements;</span></span>
- <span data-ttu-id="e3713-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="e3713-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="e3713-137">統合の改善 (クラウド、Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="e3713-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="e3713-138">2021 年 4 月 (プラットフォーム: 4.19.2104.9|エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="e3713-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="e3713-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="e3713-140">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="e3713-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="e3713-141">&ensp;プラットフォーム: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="e3713-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="e3713-142">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="e3713-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="e3713-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-144">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-144">What's new</span></span>
- <span data-ttu-id="e3713-145">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="e3713-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="e3713-146">カーネル モードのキーロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-147">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-147">Known Issues</span></span>
<span data-ttu-id="e3713-148">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-149">2021 年 3 月 (プラットフォーム: 4.19.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="e3713-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="e3713-150">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="e3713-151">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="e3713-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="e3713-152">&ensp;プラットフォーム: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="e3713-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="e3713-153">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="e3713-154">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="e3713-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-155">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-155">What's new</span></span>

- <span data-ttu-id="e3713-156">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="e3713-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="e3713-157">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="e3713-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="e3713-158">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="e3713-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-159">Known Issues</span></span>
<span data-ttu-id="e3713-160">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e3713-161">2021 年 2 月 (プラットフォーム: 4.19.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="e3713-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="e3713-162">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="e3713-163">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="e3713-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="e3713-164">&ensp;プラットフォーム: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="e3713-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="e3713-165">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="e3713-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="e3713-166">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="e3713-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-167">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-167">What's new</span></span>

- <span data-ttu-id="e3713-168">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e3713-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="e3713-169">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="e3713-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-170">Known Issues</span></span>
<span data-ttu-id="e3713-171">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="e3713-172">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="e3713-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="e3713-173">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="e3713-174">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="e3713-175">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="e3713-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="e3713-176">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e3713-177">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="e3713-178">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="e3713-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="e3713-179">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="e3713-180">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-181">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-181">What's new</span></span>

- <span data-ttu-id="e3713-182">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="e3713-183">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="e3713-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="e3713-184">Microsoft Defender ウイルス対策サービスのスパム対策機能の改善点</span><span class="sxs-lookup"><span data-stu-id="e3713-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="e3713-185">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="e3713-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="e3713-186">修正: EDR ブロック通知は、リアルタイム保護が初期検出を実行した後も脅威の履歴に残ります</span><span class="sxs-lookup"><span data-stu-id="e3713-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-187">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-187">Known Issues</span></span>
<span data-ttu-id="e3713-188">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e3713-189">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="e3713-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="e3713-190">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e3713-191">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="e3713-192">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="e3713-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="e3713-193">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e3713-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="e3713-194">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-195">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-195">What's new</span></span>

- <span data-ttu-id="e3713-196">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-197">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-197">Known Issues</span></span>
<span data-ttu-id="e3713-198">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e3713-199">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="e3713-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="e3713-200">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="e3713-201">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="e3713-202">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="e3713-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="e3713-203">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="e3713-204">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-205">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-205">What's new</span></span>

- <span data-ttu-id="e3713-206">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="e3713-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="e3713-207">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="e3713-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="e3713-208">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="e3713-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="e3713-209">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="e3713-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-210">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-210">Known Issues</span></span>

<span data-ttu-id="e3713-211">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e3713-212">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="e3713-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="e3713-213">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="e3713-214">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="e3713-215">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e3713-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="e3713-216">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="e3713-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="e3713-217">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-218">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-218">What's new</span></span>

- <span data-ttu-id="e3713-219">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="e3713-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="e3713-220">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="e3713-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="e3713-221">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="e3713-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="e3713-222">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3713-222">New management interfaces for:</span></span>
   - <span data-ttu-id="e3713-223">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="e3713-223">UDP Inspection</span></span>
   - <span data-ttu-id="e3713-224">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="e3713-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="e3713-225">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="e3713-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="e3713-226">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="e3713-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="e3713-227">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="e3713-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-228">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-228">Known Issues</span></span>

<span data-ttu-id="e3713-229">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="e3713-230">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="e3713-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="e3713-231">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="e3713-232">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="e3713-233">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="e3713-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="e3713-234">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="e3713-235">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="e3713-236">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-236">What's new</span></span>

- <span data-ttu-id="e3713-237">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="e3713-237">Add more telemetry events</span></span>
- <span data-ttu-id="e3713-238">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="e3713-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="e3713-239">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="e3713-240">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="e3713-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="e3713-241">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="e3713-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="e3713-242">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="e3713-243">Microsoft Defender ウイルス対策は、別のウイルス対策プログラムを検出すると自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="e3713-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="e3713-244">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-244">Known Issues</span></span>
<span data-ttu-id="e3713-245">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-246">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="e3713-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="e3713-247">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="e3713-248">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="e3713-249">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="e3713-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="e3713-250">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="e3713-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="e3713-251">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-252">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-252">What's new</span></span>

- <span data-ttu-id="e3713-253">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="e3713-254">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-255">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-255">Known Issues</span></span>
<span data-ttu-id="e3713-256">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-257">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="e3713-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="e3713-258">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="e3713-259">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="e3713-260">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="e3713-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="e3713-261">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="e3713-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="e3713-262">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-263">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-263">What's new</span></span>

- <span data-ttu-id="e3713-264">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="e3713-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="e3713-265">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="e3713-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="e3713-266">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="e3713-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="e3713-267">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="e3713-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="e3713-268">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="e3713-268">Fixed registry query</span></span> 
- <span data-ttu-id="e3713-269">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="e3713-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-270">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-270">Known Issues</span></span>
<span data-ttu-id="e3713-271">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-272">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="e3713-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="e3713-273">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="e3713-274">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="e3713-275">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="e3713-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="e3713-276">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="e3713-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="e3713-277">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-278">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-278">What's new</span></span>

- <span data-ttu-id="e3713-279">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="e3713-279">Improved logging for scan events</span></span>
- <span data-ttu-id="e3713-280">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="e3713-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="e3713-281">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="e3713-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="e3713-282">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="e3713-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="e3713-283">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="e3713-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="e3713-284">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="e3713-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-285">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-285">Known Issues</span></span>
<span data-ttu-id="e3713-286">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-287">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="e3713-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="e3713-288">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="e3713-289">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="e3713-290">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="e3713-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="e3713-291">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="e3713-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="e3713-292">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-293">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-293">What's new</span></span>
- <span data-ttu-id="e3713-294">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="e3713-294">WDfilter improvements</span></span>
- <span data-ttu-id="e3713-295">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="e3713-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="e3713-296">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="e3713-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="e3713-297">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="e3713-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="e3713-298">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="e3713-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="e3713-299">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="e3713-299">UEFI scan capability</span></span>
- <span data-ttu-id="e3713-300">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="e3713-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="e3713-301">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-301">Known Issues</span></span>
<span data-ttu-id="e3713-302">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-303">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="e3713-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="e3713-304">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="e3713-305">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="e3713-306">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="e3713-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="e3713-307">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="e3713-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="e3713-308">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e3713-309">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-309">What's new</span></span>

- <span data-ttu-id="e3713-310">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e3713-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="e3713-311">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="e3713-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="e3713-312">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="e3713-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="e3713-313">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="e3713-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="e3713-314">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="e3713-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e3713-315">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-315">Known Issues</span></span>
<span data-ttu-id="e3713-316">[**固定**]Microsoft Defender ウイルス対策は、スキャンを実行するときにファイルをスキップしています。</span><span class="sxs-lookup"><span data-stu-id="e3713-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="e3713-317">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="e3713-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="e3713-318">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="e3713-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="e3713-319">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="e3713-320">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="e3713-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="e3713-321">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="e3713-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="e3713-322">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e3713-323">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="e3713-324">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-324">Known Issues</span></span>
<span data-ttu-id="e3713-325">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="e3713-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-326">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="e3713-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="e3713-327">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="e3713-328">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="e3713-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="e3713-329">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="e3713-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="e3713-330">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="e3713-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="e3713-331">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="e3713-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e3713-332">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-332">What's new</span></span>

- <span data-ttu-id="e3713-333">Exchange を使用した WS2016 の固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="e3713-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="e3713-334">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="e3713-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="e3713-335">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e3713-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="e3713-336">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e3713-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="e3713-337">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="e3713-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e3713-338">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-338">Known Issues</span></span>

<span data-ttu-id="e3713-339">[**固定**] 最新の [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3713-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="e3713-340">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="e3713-341">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="e3713-341">This update is:</span></span>
> - <span data-ttu-id="e3713-342">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="e3713-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="e3713-343">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="e3713-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="e3713-344">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="e3713-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="e3713-345">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="e3713-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="e3713-346">は Windows Update でのみ [提供されます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="e3713-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e3713-347">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="e3713-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="e3713-348">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="e3713-349">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="e3713-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="e3713-350">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="e3713-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="e3713-351">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="e3713-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="e3713-352">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="e3713-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="e3713-353">新機能</span><span class="sxs-lookup"><span data-stu-id="e3713-353">What's new</span></span>

- <span data-ttu-id="e3713-354">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="e3713-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="e3713-355">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="e3713-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="e3713-356">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="e3713-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="e3713-357">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="e3713-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e3713-358">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e3713-358">Known Issues</span></span>
<span data-ttu-id="e3713-359">この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3713-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="e3713-360">Microsoft Defender ウイルス対策プラットフォームのサポート</span><span class="sxs-lookup"><span data-stu-id="e3713-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="e3713-361">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="e3713-362">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3713-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="e3713-363">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="e3713-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="e3713-364">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="e3713-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="e3713-365">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="e3713-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="e3713-366">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="e3713-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="e3713-367">\* Windows 10 リリース バージョン (Windows [10](#platform-version-included-with-windows-10-releases)リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引き続きテクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="e3713-368">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="e3713-369">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3713-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="e3713-370">Windows 10 リリースに含まれるプラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="e3713-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="e3713-371">次の表に、最新の Windows 10 リリースに同梱されている Microsoft Defender ウイルス対策プラットフォームとエンジン のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="e3713-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="e3713-372">Windows 10 リリース</span><span class="sxs-lookup"><span data-stu-id="e3713-372">Windows 10 release</span></span>  |<span data-ttu-id="e3713-373">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="e3713-373">Platform version</span></span>  |<span data-ttu-id="e3713-374">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="e3713-374">Engine version</span></span> |<span data-ttu-id="e3713-375">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="e3713-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e3713-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="e3713-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="e3713-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="e3713-377">4.18.1909.6</span></span> |<span data-ttu-id="e3713-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="e3713-378">1.1.17000.2</span></span> | <span data-ttu-id="e3713-379">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="e3713-380">1909  (19H2)</span></span> |<span data-ttu-id="e3713-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e3713-381">4.18.1902.5</span></span> |<span data-ttu-id="e3713-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="e3713-382">1.1.16700.3</span></span> | <span data-ttu-id="e3713-383">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="e3713-384">1903  (19H1)</span></span> |<span data-ttu-id="e3713-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e3713-385">4.18.1902.5</span></span> |<span data-ttu-id="e3713-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="e3713-386">1.1.15600.4</span></span> | <span data-ttu-id="e3713-387">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="e3713-388">1809  (RS5)</span></span> |<span data-ttu-id="e3713-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="e3713-389">4.18.1807.18075</span></span> |<span data-ttu-id="e3713-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="e3713-390">1.1.15000.2</span></span> | <span data-ttu-id="e3713-391">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="e3713-392">1803  (RS4)</span></span> |<span data-ttu-id="e3713-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="e3713-393">4.13.17134.1</span></span> |<span data-ttu-id="e3713-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="e3713-394">1.1.14600.4</span></span> | <span data-ttu-id="e3713-395">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="e3713-396">1709  (RS3)</span></span> |<span data-ttu-id="e3713-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="e3713-397">4.12.16299.15</span></span> |<span data-ttu-id="e3713-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="e3713-398">1.1.14104.0</span></span> | <span data-ttu-id="e3713-399">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="e3713-400">1703  (RS2)</span></span> |<span data-ttu-id="e3713-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="e3713-401">4.11.15603.2</span></span> |<span data-ttu-id="e3713-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="e3713-402">1.1.13504.0</span></span> | <span data-ttu-id="e3713-403">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e3713-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="e3713-404">1607 (RS1)</span></span> |<span data-ttu-id="e3713-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="e3713-405">4.10.14393.3683</span></span> |<span data-ttu-id="e3713-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="e3713-406">1.1.12805.0</span></span> | <span data-ttu-id="e3713-407">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="e3713-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="e3713-408">Windows 10 リリース情報については、「Windows ライフサイクル ファクト シート [」を参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="e3713-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="e3713-409">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="e3713-410">Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3713-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="e3713-411">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3713-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="e3713-412">詳細については、「Microsoft Defender update for Windows オペレーティング システム [インストール イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="e3713-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="e3713-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="e3713-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="e3713-414">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="e3713-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="e3713-415">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="e3713-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="e3713-416">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e3713-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e3713-417">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-418">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-418">Fixes</span></span>
- <span data-ttu-id="e3713-419">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-420">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-420">Additional information</span></span>
- <span data-ttu-id="e3713-421">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="e3713-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="e3713-423">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="e3713-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="e3713-424">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="e3713-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="e3713-425">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="e3713-426">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-427">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-427">Fixes</span></span>
- <span data-ttu-id="e3713-428">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-429">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-429">Additional information</span></span>
- <span data-ttu-id="e3713-430">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="e3713-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="e3713-432">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="e3713-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="e3713-433">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="e3713-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="e3713-434">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e3713-435">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-436">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-436">Fixes</span></span>
- <span data-ttu-id="e3713-437">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-438">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-438">Additional information</span></span>
- <span data-ttu-id="e3713-439">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="e3713-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="e3713-441">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="e3713-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="e3713-442">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e3713-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e3713-443">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e3713-444">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-445">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-445">Fixes</span></span>
- <span data-ttu-id="e3713-446">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-447">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-447">Additional information</span></span>
- <span data-ttu-id="e3713-448">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="e3713-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="e3713-450">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="e3713-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="e3713-451">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e3713-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e3713-452">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e3713-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="e3713-453">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-454">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-454">Fixes</span></span>
- <span data-ttu-id="e3713-455">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-456">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-456">Additional information</span></span>
- <span data-ttu-id="e3713-457">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="e3713-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="e3713-459">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="e3713-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="e3713-460">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e3713-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e3713-461">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e3713-462">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-463">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-463">Fixes</span></span>
- <span data-ttu-id="e3713-464">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-465">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-465">Additional information</span></span>
- <span data-ttu-id="e3713-466">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="e3713-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="e3713-468">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="e3713-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="e3713-469">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e3713-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e3713-470">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e3713-471">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-472">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-472">Fixes</span></span>
- <span data-ttu-id="e3713-473">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-474">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-474">Additional information</span></span>
- <span data-ttu-id="e3713-475">Microsoft Defender ウイルス対策署名の更新</span><span class="sxs-lookup"><span data-stu-id="e3713-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="e3713-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="e3713-477">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e3713-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e3713-478">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e3713-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="e3713-479">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e3713-480">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-481">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-481">Fixes</span></span>
- <span data-ttu-id="e3713-482">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-483">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-483">Additional information</span></span>
- <span data-ttu-id="e3713-484">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e3713-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="e3713-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="e3713-486">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e3713-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e3713-487">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="e3713-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="e3713-488">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e3713-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="e3713-489">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="e3713-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e3713-490">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-490">Fixes</span></span>
- <span data-ttu-id="e3713-491">なし</span><span class="sxs-lookup"><span data-stu-id="e3713-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e3713-492">追加情報</span><span class="sxs-lookup"><span data-stu-id="e3713-492">Additional information</span></span>
- <span data-ttu-id="e3713-493">Windows 10 RS1 以降の OS インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e3713-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="e3713-494">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="e3713-494">Additional resources</span></span>

| <span data-ttu-id="e3713-495">記事</span><span class="sxs-lookup"><span data-stu-id="e3713-495">Article</span></span> | <span data-ttu-id="e3713-496">説明</span><span class="sxs-lookup"><span data-stu-id="e3713-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="e3713-497">Windows オペレーティング システムのインストール イメージ用の Microsoft Defender 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3713-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="e3713-498">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3713-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="e3713-499">Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 インストール イメージの Microsoft Defender ウイルス対策更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3713-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="e3713-500">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="e3713-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e3713-501">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="e3713-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="e3713-502">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="e3713-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="e3713-503">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e3713-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="e3713-504">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="e3713-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="e3713-505">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e3713-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="e3713-506">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="e3713-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e3713-507">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="e3713-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="e3713-508">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="e3713-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="e3713-509">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3713-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
