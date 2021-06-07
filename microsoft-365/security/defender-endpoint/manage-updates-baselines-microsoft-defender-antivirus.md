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
ms.openlocfilehash: 264a3b7a4a24c446048d6cfc6863f1ae9765566f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789185"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="7ce06-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="7ce06-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="7ce06-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7ce06-105">**Applies to:**</span></span>

- [<span data-ttu-id="7ce06-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ce06-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="7ce06-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="7ce06-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="7ce06-108">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="7ce06-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-109">Security intelligence updates</span></span>
- <span data-ttu-id="7ce06-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="7ce06-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ce06-111">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="7ce06-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="7ce06-112">パッシブ モードで実行されている場合でも、Microsoft Defender ウイルス対策保護を[更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="7ce06-113">最新のエンジン、プラットフォーム、署名日を確認するには、セキュリティ インテリジェンスの更新プログラム (Microsoft Defender ウイルス対策その他の Microsoft マルウェア対策に関する[ページをご覧ください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="7ce06-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-114">Security intelligence updates</span></span>

<span data-ttu-id="7ce06-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ce06-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="7ce06-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="7ce06-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="7ce06-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="7ce06-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="7ce06-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="7ce06-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="7ce06-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="7ce06-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7ce06-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="7ce06-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="7ce06-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="7ce06-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="7ce06-124">Product updates</span></span>

<span data-ttu-id="7ce06-125">Microsoft Defender ウイルス対策月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、各リリースと共に主要な機能更新プログラムWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="7ce06-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="7ce06-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="7ce06-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="7ce06-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7ce06-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="7ce06-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="7ce06-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="7ce06-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="7ce06-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="7ce06-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="7ce06-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="7ce06-133">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="7ce06-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="7ce06-134">All our updates contain</span></span> 
- <span data-ttu-id="7ce06-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="7ce06-135">performance improvements;</span></span>
- <span data-ttu-id="7ce06-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="7ce06-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="7ce06-137">統合の改善 (クラウド、Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="7ce06-138">May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="7ce06-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="7ce06-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="7ce06-140">&ensp;リリース: **2021 年 6 月 4 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="7ce06-141">&ensp;プラットフォーム: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="7ce06-142">&ensp;エンジン: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="7ce06-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="7ce06-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-144">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-144">What's new</span></span>
- <span data-ttu-id="7ce06-145">動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-145">Improvements to behavior monitoring</span></span> 

### <a name="known-issues"></a><span data-ttu-id="7ce06-146">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-146">Known Issues</span></span>
<span data-ttu-id="7ce06-147">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-147">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7ce06-148">2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="7ce06-148">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="7ce06-149">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-149">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="7ce06-150">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="7ce06-150">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="7ce06-151">&ensp;プラットフォーム: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="7ce06-151">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="7ce06-152">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="7ce06-153">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="7ce06-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-154">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-154">What's new</span></span>
- <span data-ttu-id="7ce06-155">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="7ce06-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="7ce06-156">カーネル モードのキーロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-157">Known Issues</span></span>
<span data-ttu-id="7ce06-158">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7ce06-159">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="7ce06-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="7ce06-160">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="7ce06-161">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="7ce06-161">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="7ce06-162">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="7ce06-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="7ce06-163">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="7ce06-164">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="7ce06-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-165">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-165">What's new</span></span>

- <span data-ttu-id="7ce06-166">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="7ce06-167">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="7ce06-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="7ce06-168">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="7ce06-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-169">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-169">Known Issues</span></span>
<span data-ttu-id="7ce06-170">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="7ce06-171">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="7ce06-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="7ce06-172">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="7ce06-173">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="7ce06-174">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="7ce06-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="7ce06-175">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="7ce06-176">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="7ce06-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="7ce06-177">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="7ce06-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="7ce06-178">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="7ce06-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="7ce06-179">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-180">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-180">What's new</span></span>

- <span data-ttu-id="7ce06-181">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7ce06-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="7ce06-182">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="7ce06-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-183">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-183">Known Issues</span></span>
<span data-ttu-id="7ce06-184">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7ce06-185">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="7ce06-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="7ce06-186">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="7ce06-187">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="7ce06-188">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="7ce06-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="7ce06-189">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="7ce06-190">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-191">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-191">What's new</span></span>

- <span data-ttu-id="7ce06-192">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="7ce06-193">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="7ce06-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="7ce06-194">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="7ce06-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="7ce06-195">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="7ce06-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="7ce06-196">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="7ce06-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-197">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-197">Known Issues</span></span>
<span data-ttu-id="7ce06-198">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7ce06-199">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="7ce06-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="7ce06-200">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="7ce06-201">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="7ce06-202">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="7ce06-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="7ce06-203">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="7ce06-204">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-205">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-205">What's new</span></span>

- <span data-ttu-id="7ce06-206">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-207">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-207">Known Issues</span></span>
<span data-ttu-id="7ce06-208">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7ce06-209">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="7ce06-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="7ce06-210">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="7ce06-211">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="7ce06-212">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="7ce06-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="7ce06-213">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="7ce06-214">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-215">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-215">What's new</span></span>

- <span data-ttu-id="7ce06-216">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="7ce06-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="7ce06-217">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="7ce06-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="7ce06-218">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="7ce06-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="7ce06-219">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="7ce06-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-220">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-220">Known Issues</span></span>

<span data-ttu-id="7ce06-221">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7ce06-222">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="7ce06-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="7ce06-223">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="7ce06-224">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="7ce06-225">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="7ce06-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="7ce06-226">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="7ce06-227">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-228">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-228">What's new</span></span>

- <span data-ttu-id="7ce06-229">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="7ce06-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="7ce06-230">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="7ce06-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="7ce06-231">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="7ce06-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="7ce06-232">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ce06-232">New management interfaces for:</span></span>
   - <span data-ttu-id="7ce06-233">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="7ce06-233">UDP Inspection</span></span>
   - <span data-ttu-id="7ce06-234">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="7ce06-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="7ce06-235">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="7ce06-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="7ce06-236">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="7ce06-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="7ce06-237">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-238">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-238">Known Issues</span></span>

<span data-ttu-id="7ce06-239">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="7ce06-240">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="7ce06-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="7ce06-241">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="7ce06-242">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="7ce06-243">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="7ce06-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="7ce06-244">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="7ce06-245">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="7ce06-246">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-246">What's new</span></span>

- <span data-ttu-id="7ce06-247">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="7ce06-247">Add more telemetry events</span></span>
- <span data-ttu-id="7ce06-248">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="7ce06-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="7ce06-249">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="7ce06-250">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="7ce06-251">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="7ce06-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="7ce06-252">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="7ce06-253">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="7ce06-254">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-254">Known Issues</span></span>
<span data-ttu-id="7ce06-255">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-256">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="7ce06-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="7ce06-257">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="7ce06-258">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="7ce06-259">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="7ce06-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="7ce06-260">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="7ce06-261">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-262">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-262">What's new</span></span>

- <span data-ttu-id="7ce06-263">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="7ce06-264">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-265">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-265">Known Issues</span></span>
<span data-ttu-id="7ce06-266">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-267">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="7ce06-268">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="7ce06-269">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="7ce06-270">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="7ce06-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="7ce06-271">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="7ce06-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="7ce06-272">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-273">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-273">What's new</span></span>

- <span data-ttu-id="7ce06-274">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="7ce06-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="7ce06-275">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="7ce06-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="7ce06-276">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="7ce06-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="7ce06-277">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="7ce06-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="7ce06-278">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="7ce06-278">Fixed registry query</span></span> 
- <span data-ttu-id="7ce06-279">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="7ce06-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-280">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-280">Known Issues</span></span>
<span data-ttu-id="7ce06-281">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-282">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="7ce06-283">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="7ce06-284">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="7ce06-285">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="7ce06-286">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="7ce06-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="7ce06-287">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-288">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-288">What's new</span></span>

- <span data-ttu-id="7ce06-289">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="7ce06-289">Improved logging for scan events</span></span>
- <span data-ttu-id="7ce06-290">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="7ce06-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="7ce06-291">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="7ce06-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="7ce06-292">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="7ce06-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="7ce06-293">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="7ce06-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="7ce06-294">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="7ce06-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-295">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-295">Known Issues</span></span>
<span data-ttu-id="7ce06-296">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-297">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="7ce06-298">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="7ce06-299">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="7ce06-300">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="7ce06-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="7ce06-301">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="7ce06-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="7ce06-302">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-303">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-303">What's new</span></span>
- <span data-ttu-id="7ce06-304">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="7ce06-304">WDfilter improvements</span></span>
- <span data-ttu-id="7ce06-305">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="7ce06-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="7ce06-306">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="7ce06-307">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="7ce06-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="7ce06-308">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="7ce06-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="7ce06-309">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-309">UEFI scan capability</span></span>
- <span data-ttu-id="7ce06-310">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="7ce06-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="7ce06-311">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-311">Known Issues</span></span>
<span data-ttu-id="7ce06-312">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-313">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="7ce06-314">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="7ce06-315">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="7ce06-316">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="7ce06-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="7ce06-317">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="7ce06-318">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7ce06-319">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-319">What's new</span></span>

- <span data-ttu-id="7ce06-320">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7ce06-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="7ce06-321">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="7ce06-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="7ce06-322">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="7ce06-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="7ce06-323">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="7ce06-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="7ce06-324">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="7ce06-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7ce06-325">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-325">Known Issues</span></span>
<span data-ttu-id="7ce06-326">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="7ce06-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="7ce06-327">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="7ce06-328">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="7ce06-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="7ce06-329">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="7ce06-330">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="7ce06-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="7ce06-331">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="7ce06-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="7ce06-332">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="7ce06-333">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="7ce06-334">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-334">Known Issues</span></span>
<span data-ttu-id="7ce06-335">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="7ce06-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-336">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="7ce06-337">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="7ce06-338">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="7ce06-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="7ce06-339">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="7ce06-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="7ce06-340">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="7ce06-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="7ce06-341">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="7ce06-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="7ce06-342">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-342">What's new</span></span>

- <span data-ttu-id="7ce06-343">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="7ce06-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="7ce06-344">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="7ce06-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="7ce06-345">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7ce06-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="7ce06-346">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="7ce06-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="7ce06-347">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="7ce06-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7ce06-348">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-348">Known Issues</span></span>

<span data-ttu-id="7ce06-349">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="7ce06-350">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="7ce06-351">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="7ce06-351">This update is:</span></span>
> - <span data-ttu-id="7ce06-352">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="7ce06-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="7ce06-353">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="7ce06-354">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="7ce06-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="7ce06-355">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="7ce06-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="7ce06-356">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="7ce06-357">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="7ce06-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="7ce06-358">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="7ce06-359">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="7ce06-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="7ce06-360">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="7ce06-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="7ce06-361">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="7ce06-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="7ce06-362">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="7ce06-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="7ce06-363">新機能</span><span class="sxs-lookup"><span data-stu-id="7ce06-363">What's new</span></span>

- <span data-ttu-id="7ce06-364">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="7ce06-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="7ce06-365">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="7ce06-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="7ce06-366">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="7ce06-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="7ce06-367">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="7ce06-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7ce06-368">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ce06-368">Known Issues</span></span>
<span data-ttu-id="7ce06-369">この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="7ce06-369">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="7ce06-370">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="7ce06-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="7ce06-371">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="7ce06-372">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="7ce06-373">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="7ce06-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="7ce06-374">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="7ce06-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="7ce06-375">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="7ce06-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="7ce06-376">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="7ce06-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="7ce06-377">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="7ce06-378">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="7ce06-379">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="7ce06-380">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="7ce06-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="7ce06-381">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="7ce06-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="7ce06-382">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="7ce06-382">Windows 10 release</span></span>  |<span data-ttu-id="7ce06-383">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="7ce06-383">Platform version</span></span>  |<span data-ttu-id="7ce06-384">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="7ce06-384">Engine version</span></span> |<span data-ttu-id="7ce06-385">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="7ce06-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="7ce06-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="7ce06-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="7ce06-387">4.18.1909.6</span></span> |<span data-ttu-id="7ce06-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="7ce06-388">1.1.17000.2</span></span> | <span data-ttu-id="7ce06-389">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-390">1909  (19H2)</span></span> |<span data-ttu-id="7ce06-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="7ce06-391">4.18.1902.5</span></span> |<span data-ttu-id="7ce06-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="7ce06-392">1.1.16700.3</span></span> | <span data-ttu-id="7ce06-393">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="7ce06-394">1903  (19H1)</span></span> |<span data-ttu-id="7ce06-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="7ce06-395">4.18.1902.5</span></span> |<span data-ttu-id="7ce06-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="7ce06-396">1.1.15600.4</span></span> | <span data-ttu-id="7ce06-397">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="7ce06-398">1809  (RS5)</span></span> |<span data-ttu-id="7ce06-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="7ce06-399">4.18.1807.18075</span></span> |<span data-ttu-id="7ce06-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="7ce06-400">1.1.15000.2</span></span> | <span data-ttu-id="7ce06-401">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="7ce06-402">1803  (RS4)</span></span> |<span data-ttu-id="7ce06-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="7ce06-403">4.13.17134.1</span></span> |<span data-ttu-id="7ce06-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="7ce06-404">1.1.14600.4</span></span> | <span data-ttu-id="7ce06-405">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="7ce06-406">1709  (RS3)</span></span> |<span data-ttu-id="7ce06-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="7ce06-407">4.12.16299.15</span></span> |<span data-ttu-id="7ce06-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="7ce06-408">1.1.14104.0</span></span> | <span data-ttu-id="7ce06-409">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="7ce06-410">1703  (RS2)</span></span> |<span data-ttu-id="7ce06-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="7ce06-411">4.11.15603.2</span></span> |<span data-ttu-id="7ce06-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="7ce06-412">1.1.13504.0</span></span> | <span data-ttu-id="7ce06-413">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7ce06-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="7ce06-414">1607 (RS1)</span></span> |<span data-ttu-id="7ce06-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="7ce06-415">4.10.14393.3683</span></span> |<span data-ttu-id="7ce06-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="7ce06-416">1.1.12805.0</span></span> | <span data-ttu-id="7ce06-417">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="7ce06-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="7ce06-418">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="7ce06-419">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="7ce06-420">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ce06-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="7ce06-421">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="7ce06-422">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="7ce06-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="7ce06-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="7ce06-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="7ce06-424">&ensp;パッケージ のバージョン: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="7ce06-425">&ensp;プラットフォーム のバージョン: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="7ce06-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="7ce06-426">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="7ce06-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="7ce06-427">&ensp;署名バージョン: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-428">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-428">Fixes</span></span>
- <span data-ttu-id="7ce06-429">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-430">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-430">Additional information</span></span>
- <span data-ttu-id="7ce06-431">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="7ce06-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="7ce06-433">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="7ce06-434">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="7ce06-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="7ce06-435">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="7ce06-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="7ce06-436">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-437">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-437">Fixes</span></span>
- <span data-ttu-id="7ce06-438">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-439">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-439">Additional information</span></span>
- <span data-ttu-id="7ce06-440">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="7ce06-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="7ce06-442">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="7ce06-443">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="7ce06-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="7ce06-444">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="7ce06-445">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-446">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-446">Fixes</span></span>
- <span data-ttu-id="7ce06-447">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-448">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-448">Additional information</span></span>
- <span data-ttu-id="7ce06-449">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="7ce06-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="7ce06-451">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="7ce06-452">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="7ce06-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="7ce06-453">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="7ce06-454">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-455">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-455">Fixes</span></span>
- <span data-ttu-id="7ce06-456">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-457">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-457">Additional information</span></span>
- <span data-ttu-id="7ce06-458">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="7ce06-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="7ce06-460">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="7ce06-461">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="7ce06-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="7ce06-462">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="7ce06-463">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-464">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-464">Fixes</span></span>
- <span data-ttu-id="7ce06-465">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-466">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-466">Additional information</span></span>
- <span data-ttu-id="7ce06-467">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="7ce06-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="7ce06-469">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="7ce06-470">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="7ce06-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="7ce06-471">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="7ce06-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="7ce06-472">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-473">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-473">Fixes</span></span>
- <span data-ttu-id="7ce06-474">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-475">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-475">Additional information</span></span>
- <span data-ttu-id="7ce06-476">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="7ce06-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="7ce06-478">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="7ce06-479">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="7ce06-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="7ce06-480">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7ce06-481">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-482">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-482">Fixes</span></span>
- <span data-ttu-id="7ce06-483">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-484">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-484">Additional information</span></span>
- <span data-ttu-id="7ce06-485">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="7ce06-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="7ce06-487">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="7ce06-488">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="7ce06-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="7ce06-489">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7ce06-490">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-491">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-491">Fixes</span></span>
- <span data-ttu-id="7ce06-492">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-493">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-493">Additional information</span></span>
- <span data-ttu-id="7ce06-494">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="7ce06-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="7ce06-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="7ce06-496">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="7ce06-497">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="7ce06-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="7ce06-498">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7ce06-499">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-500">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-500">Fixes</span></span>
- <span data-ttu-id="7ce06-501">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-502">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-502">Additional information</span></span>
- <span data-ttu-id="7ce06-503">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7ce06-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="7ce06-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="7ce06-505">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="7ce06-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="7ce06-506">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="7ce06-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="7ce06-507">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="7ce06-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="7ce06-508">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="7ce06-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7ce06-509">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-509">Fixes</span></span>
- <span data-ttu-id="7ce06-510">なし</span><span class="sxs-lookup"><span data-stu-id="7ce06-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7ce06-511">追加情報</span><span class="sxs-lookup"><span data-stu-id="7ce06-511">Additional information</span></span>
- <span data-ttu-id="7ce06-512">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="7ce06-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="7ce06-513">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="7ce06-513">Additional resources</span></span>

| <span data-ttu-id="7ce06-514">記事</span><span class="sxs-lookup"><span data-stu-id="7ce06-514">Article</span></span> | <span data-ttu-id="7ce06-515">説明</span><span class="sxs-lookup"><span data-stu-id="7ce06-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="7ce06-516">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="7ce06-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="7ce06-517">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ce06-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="7ce06-518">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ce06-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="7ce06-519">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="7ce06-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="7ce06-520">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="7ce06-521">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="7ce06-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="7ce06-522">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="7ce06-523">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="7ce06-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="7ce06-524">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="7ce06-525">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="7ce06-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="7ce06-526">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="7ce06-527">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="7ce06-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="7ce06-528">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7ce06-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
