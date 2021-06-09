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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822276"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="37294-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="37294-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="37294-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="37294-105">**Applies to:**</span></span>

- [<span data-ttu-id="37294-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37294-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="37294-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="37294-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="37294-108">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="37294-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="37294-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-109">Security intelligence updates</span></span>
- <span data-ttu-id="37294-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="37294-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37294-111">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="37294-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="37294-112">パッシブ モードで実行されている場合でも、Microsoft Defender ウイルス対策保護を[更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="37294-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="37294-113">最新のエンジン、プラットフォーム、署名日を確認するには、セキュリティ インテリジェンスの更新プログラム (Microsoft Defender ウイルス対策その他の Microsoft マルウェア対策に関する[ページをご覧ください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="37294-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="37294-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-114">Security intelligence updates</span></span>

<span data-ttu-id="37294-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="37294-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="37294-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="37294-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="37294-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="37294-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="37294-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="37294-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="37294-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37294-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="37294-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="37294-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="37294-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="37294-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="37294-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="37294-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="37294-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="37294-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="37294-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="37294-124">Product updates</span></span>

<span data-ttu-id="37294-125">Microsoft Defender ウイルス対策月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、各リリースと共に主要な機能更新プログラムWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="37294-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="37294-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="37294-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="37294-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="37294-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="37294-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="37294-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="37294-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="37294-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="37294-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="37294-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="37294-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="37294-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="37294-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="37294-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="37294-133">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="37294-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="37294-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="37294-134">All our updates contain</span></span> 
- <span data-ttu-id="37294-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="37294-135">performance improvements;</span></span>
- <span data-ttu-id="37294-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="37294-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="37294-137">統合の改善 (Cloud、Microsoft 365 [Defender)。](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="37294-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="37294-138">May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="37294-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="37294-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="37294-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="37294-140">&ensp;リリース: **2021 年 6 月 4 日**</span><span class="sxs-lookup"><span data-stu-id="37294-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="37294-141">&ensp;プラットフォーム: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="37294-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="37294-142">&ensp;エンジン: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="37294-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="37294-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="37294-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-144">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-144">What's new</span></span>
- <span data-ttu-id="37294-145">動作監視 [の改善](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="37294-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="37294-146">固定 [ネットワーク保護通知](network-protection.md) フィルター機能</span><span class="sxs-lookup"><span data-stu-id="37294-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-147">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-147">Known Issues</span></span>
<span data-ttu-id="37294-148">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="37294-149">2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="37294-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="37294-150">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="37294-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="37294-151">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="37294-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="37294-152">&ensp;プラットフォーム: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="37294-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="37294-153">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="37294-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="37294-154">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="37294-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-155">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-155">What's new</span></span>
- <span data-ttu-id="37294-156">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="37294-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="37294-157">カーネル モードのキーロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="37294-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="37294-158">Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール [が追加されました](updates.md)</span><span class="sxs-lookup"><span data-stu-id="37294-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-159">Known Issues</span></span>
<span data-ttu-id="37294-160">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="37294-161">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="37294-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="37294-162">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="37294-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="37294-163">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="37294-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="37294-164">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="37294-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="37294-165">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="37294-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="37294-166">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="37294-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-167">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-167">What's new</span></span>

- <span data-ttu-id="37294-168">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="37294-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="37294-169">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="37294-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="37294-170">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="37294-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-171">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-171">Known Issues</span></span>
<span data-ttu-id="37294-172">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="37294-173">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="37294-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="37294-174">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="37294-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="37294-175">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="37294-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="37294-176">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="37294-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="37294-177">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="37294-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="37294-178">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="37294-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="37294-179">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="37294-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="37294-180">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="37294-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="37294-181">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-182">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-182">What's new</span></span>

- <span data-ttu-id="37294-183">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="37294-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="37294-184">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="37294-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-185">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-185">Known Issues</span></span>
<span data-ttu-id="37294-186">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="37294-187">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="37294-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="37294-188">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="37294-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="37294-189">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="37294-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="37294-190">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="37294-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="37294-191">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="37294-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="37294-192">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-193">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-193">What's new</span></span>

- <span data-ttu-id="37294-194">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="37294-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="37294-195">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="37294-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="37294-196">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="37294-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="37294-197">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="37294-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="37294-198">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="37294-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-199">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-199">Known Issues</span></span>
<span data-ttu-id="37294-200">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="37294-201">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="37294-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="37294-202">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="37294-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="37294-203">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="37294-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="37294-204">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="37294-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="37294-205">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="37294-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="37294-206">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-207">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-207">What's new</span></span>

- <span data-ttu-id="37294-208">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="37294-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-209">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-209">Known Issues</span></span>
<span data-ttu-id="37294-210">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="37294-211">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="37294-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="37294-212">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="37294-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="37294-213">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="37294-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="37294-214">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="37294-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="37294-215">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="37294-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="37294-216">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-217">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-217">What's new</span></span>

- <span data-ttu-id="37294-218">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="37294-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="37294-219">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="37294-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="37294-220">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="37294-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="37294-221">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="37294-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-222">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-222">Known Issues</span></span>

<span data-ttu-id="37294-223">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="37294-224">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="37294-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="37294-225">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="37294-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="37294-226">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="37294-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="37294-227">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="37294-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="37294-228">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="37294-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="37294-229">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-230">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-230">What's new</span></span>

- <span data-ttu-id="37294-231">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="37294-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="37294-232">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="37294-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="37294-233">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="37294-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="37294-234">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37294-234">New management interfaces for:</span></span>
   - <span data-ttu-id="37294-235">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="37294-235">UDP Inspection</span></span>
   - <span data-ttu-id="37294-236">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="37294-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="37294-237">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="37294-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="37294-238">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="37294-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="37294-239">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="37294-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-240">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-240">Known Issues</span></span>

<span data-ttu-id="37294-241">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="37294-242">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="37294-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="37294-243">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="37294-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="37294-244">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="37294-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="37294-245">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="37294-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="37294-246">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="37294-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="37294-247">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="37294-248">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-248">What's new</span></span>

- <span data-ttu-id="37294-249">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="37294-249">Add more telemetry events</span></span>
- <span data-ttu-id="37294-250">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="37294-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="37294-251">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="37294-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="37294-252">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="37294-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="37294-253">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="37294-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="37294-254">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="37294-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="37294-255">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="37294-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="37294-256">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-256">Known Issues</span></span>
<span data-ttu-id="37294-257">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-258">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="37294-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="37294-259">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="37294-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="37294-260">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="37294-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="37294-261">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="37294-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="37294-262">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="37294-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="37294-263">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-264">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-264">What's new</span></span>

- <span data-ttu-id="37294-265">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="37294-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="37294-266">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="37294-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-267">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-267">Known Issues</span></span>
<span data-ttu-id="37294-268">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-269">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="37294-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="37294-270">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="37294-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="37294-271">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="37294-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="37294-272">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="37294-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="37294-273">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="37294-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="37294-274">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-275">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-275">What's new</span></span>

- <span data-ttu-id="37294-276">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="37294-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="37294-277">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="37294-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="37294-278">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="37294-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="37294-279">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="37294-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="37294-280">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="37294-280">Fixed registry query</span></span> 
- <span data-ttu-id="37294-281">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="37294-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-282">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-282">Known Issues</span></span>
<span data-ttu-id="37294-283">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-284">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="37294-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="37294-285">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="37294-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="37294-286">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="37294-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="37294-287">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="37294-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="37294-288">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="37294-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="37294-289">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-290">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-290">What's new</span></span>

- <span data-ttu-id="37294-291">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="37294-291">Improved logging for scan events</span></span>
- <span data-ttu-id="37294-292">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="37294-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="37294-293">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="37294-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="37294-294">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="37294-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="37294-295">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="37294-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="37294-296">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="37294-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-297">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-297">Known Issues</span></span>
<span data-ttu-id="37294-298">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-299">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="37294-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="37294-300">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="37294-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="37294-301">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="37294-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="37294-302">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="37294-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="37294-303">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="37294-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="37294-304">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-305">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-305">What's new</span></span>
- <span data-ttu-id="37294-306">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="37294-306">WDfilter improvements</span></span>
- <span data-ttu-id="37294-307">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="37294-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="37294-308">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="37294-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="37294-309">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="37294-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="37294-310">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="37294-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="37294-311">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="37294-311">UEFI scan capability</span></span>
- <span data-ttu-id="37294-312">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="37294-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="37294-313">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-313">Known Issues</span></span>
<span data-ttu-id="37294-314">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-315">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="37294-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="37294-316">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="37294-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="37294-317">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="37294-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="37294-318">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="37294-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="37294-319">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="37294-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="37294-320">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="37294-321">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-321">What's new</span></span>

- <span data-ttu-id="37294-322">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="37294-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="37294-323">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="37294-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="37294-324">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="37294-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="37294-325">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="37294-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="37294-326">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="37294-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="37294-327">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-327">Known Issues</span></span>
<span data-ttu-id="37294-328">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="37294-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="37294-329">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="37294-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="37294-330">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="37294-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="37294-331">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="37294-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="37294-332">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="37294-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="37294-333">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="37294-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="37294-334">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="37294-335">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="37294-336">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-336">Known Issues</span></span>
<span data-ttu-id="37294-337">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="37294-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-338">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="37294-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="37294-339">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="37294-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="37294-340">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="37294-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="37294-341">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="37294-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="37294-342">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="37294-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="37294-343">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="37294-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="37294-344">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-344">What's new</span></span>

- <span data-ttu-id="37294-345">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="37294-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="37294-346">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="37294-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="37294-347">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="37294-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="37294-348">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="37294-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="37294-349">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="37294-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="37294-350">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-350">Known Issues</span></span>

<span data-ttu-id="37294-351">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37294-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="37294-352">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="37294-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="37294-353">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="37294-353">This update is:</span></span>
> - <span data-ttu-id="37294-354">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="37294-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="37294-355">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="37294-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="37294-356">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="37294-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="37294-357">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="37294-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="37294-358">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="37294-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="37294-359">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="37294-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="37294-360">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="37294-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="37294-361">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="37294-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="37294-362">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="37294-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="37294-363">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="37294-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="37294-364">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="37294-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="37294-365">新機能</span><span class="sxs-lookup"><span data-stu-id="37294-365">What's new</span></span>

- <span data-ttu-id="37294-366">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="37294-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="37294-367">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="37294-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="37294-368">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="37294-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="37294-369">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="37294-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="37294-370">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37294-370">Known Issues</span></span>
<span data-ttu-id="37294-371">この更新プログラムをインストールすると、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.18.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="37294-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="37294-372">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="37294-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="37294-373">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="37294-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="37294-374">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="37294-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="37294-375">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="37294-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="37294-376">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="37294-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="37294-377">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="37294-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="37294-378">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="37294-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="37294-379">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="37294-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="37294-380">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="37294-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="37294-381">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37294-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="37294-382">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="37294-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="37294-383">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="37294-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="37294-384">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="37294-384">Windows 10 release</span></span>  |<span data-ttu-id="37294-385">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="37294-385">Platform version</span></span>  |<span data-ttu-id="37294-386">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="37294-386">Engine version</span></span> |<span data-ttu-id="37294-387">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="37294-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="37294-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="37294-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="37294-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="37294-389">4.18.1909.6</span></span> |<span data-ttu-id="37294-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="37294-390">1.1.17000.2</span></span> | <span data-ttu-id="37294-391">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="37294-392">1909  (19H2)</span></span> |<span data-ttu-id="37294-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="37294-393">4.18.1902.5</span></span> |<span data-ttu-id="37294-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="37294-394">1.1.16700.3</span></span> | <span data-ttu-id="37294-395">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="37294-396">1903  (19H1)</span></span> |<span data-ttu-id="37294-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="37294-397">4.18.1902.5</span></span> |<span data-ttu-id="37294-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="37294-398">1.1.15600.4</span></span> | <span data-ttu-id="37294-399">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="37294-400">1809  (RS5)</span></span> |<span data-ttu-id="37294-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="37294-401">4.18.1807.18075</span></span> |<span data-ttu-id="37294-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="37294-402">1.1.15000.2</span></span> | <span data-ttu-id="37294-403">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="37294-404">1803  (RS4)</span></span> |<span data-ttu-id="37294-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="37294-405">4.13.17134.1</span></span> |<span data-ttu-id="37294-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="37294-406">1.1.14600.4</span></span> | <span data-ttu-id="37294-407">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="37294-408">1709  (RS3)</span></span> |<span data-ttu-id="37294-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="37294-409">4.12.16299.15</span></span> |<span data-ttu-id="37294-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="37294-410">1.1.14104.0</span></span> | <span data-ttu-id="37294-411">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="37294-412">1703  (RS2)</span></span> |<span data-ttu-id="37294-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="37294-413">4.11.15603.2</span></span> |<span data-ttu-id="37294-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="37294-414">1.1.13504.0</span></span> | <span data-ttu-id="37294-415">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="37294-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="37294-416">1607 (RS1)</span></span> |<span data-ttu-id="37294-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="37294-417">4.10.14393.3683</span></span> |<span data-ttu-id="37294-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="37294-418">1.1.12805.0</span></span> | <span data-ttu-id="37294-419">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="37294-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="37294-420">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="37294-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="37294-421">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="37294-422">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37294-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="37294-423">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="37294-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="37294-424">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="37294-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="37294-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="37294-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="37294-426">&ensp;パッケージ のバージョン: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="37294-427">&ensp;プラットフォーム のバージョン: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="37294-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="37294-428">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="37294-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="37294-429">&ensp;署名バージョン: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="37294-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-430">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-430">Fixes</span></span>
- <span data-ttu-id="37294-431">なし</span><span class="sxs-lookup"><span data-stu-id="37294-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-432">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-432">Additional information</span></span>
- <span data-ttu-id="37294-433">なし</span><span class="sxs-lookup"><span data-stu-id="37294-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="37294-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="37294-435">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="37294-436">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="37294-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="37294-437">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="37294-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="37294-438">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="37294-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-439">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-439">Fixes</span></span>
- <span data-ttu-id="37294-440">なし</span><span class="sxs-lookup"><span data-stu-id="37294-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-441">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-441">Additional information</span></span>
- <span data-ttu-id="37294-442">なし</span><span class="sxs-lookup"><span data-stu-id="37294-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="37294-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="37294-444">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="37294-445">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="37294-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="37294-446">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="37294-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="37294-447">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="37294-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-448">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-448">Fixes</span></span>
- <span data-ttu-id="37294-449">なし</span><span class="sxs-lookup"><span data-stu-id="37294-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-450">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-450">Additional information</span></span>
- <span data-ttu-id="37294-451">なし</span><span class="sxs-lookup"><span data-stu-id="37294-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="37294-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="37294-453">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="37294-454">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="37294-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="37294-455">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="37294-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="37294-456">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="37294-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-457">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-457">Fixes</span></span>
- <span data-ttu-id="37294-458">なし</span><span class="sxs-lookup"><span data-stu-id="37294-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-459">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-459">Additional information</span></span>
- <span data-ttu-id="37294-460">なし</span><span class="sxs-lookup"><span data-stu-id="37294-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="37294-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="37294-462">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="37294-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="37294-463">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="37294-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="37294-464">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="37294-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="37294-465">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="37294-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-466">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-466">Fixes</span></span>
- <span data-ttu-id="37294-467">なし</span><span class="sxs-lookup"><span data-stu-id="37294-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-468">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-468">Additional information</span></span>
- <span data-ttu-id="37294-469">なし</span><span class="sxs-lookup"><span data-stu-id="37294-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="37294-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="37294-471">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="37294-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="37294-472">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="37294-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="37294-473">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="37294-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="37294-474">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="37294-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-475">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-475">Fixes</span></span>
- <span data-ttu-id="37294-476">なし</span><span class="sxs-lookup"><span data-stu-id="37294-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-477">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-477">Additional information</span></span>
- <span data-ttu-id="37294-478">なし</span><span class="sxs-lookup"><span data-stu-id="37294-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="37294-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="37294-480">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="37294-481">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="37294-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="37294-482">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="37294-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="37294-483">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="37294-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-484">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-484">Fixes</span></span>
- <span data-ttu-id="37294-485">なし</span><span class="sxs-lookup"><span data-stu-id="37294-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-486">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-486">Additional information</span></span>
- <span data-ttu-id="37294-487">なし</span><span class="sxs-lookup"><span data-stu-id="37294-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="37294-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="37294-489">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="37294-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="37294-490">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="37294-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="37294-491">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="37294-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="37294-492">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="37294-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-493">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-493">Fixes</span></span>
- <span data-ttu-id="37294-494">なし</span><span class="sxs-lookup"><span data-stu-id="37294-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-495">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-495">Additional information</span></span>
- <span data-ttu-id="37294-496">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="37294-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="37294-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="37294-498">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="37294-499">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="37294-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="37294-500">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="37294-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="37294-501">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="37294-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-502">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-502">Fixes</span></span>
- <span data-ttu-id="37294-503">なし</span><span class="sxs-lookup"><span data-stu-id="37294-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-504">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-504">Additional information</span></span>
- <span data-ttu-id="37294-505">なし</span><span class="sxs-lookup"><span data-stu-id="37294-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="37294-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="37294-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="37294-507">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="37294-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="37294-508">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="37294-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="37294-509">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="37294-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="37294-510">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="37294-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="37294-511">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-511">Fixes</span></span>
- <span data-ttu-id="37294-512">なし</span><span class="sxs-lookup"><span data-stu-id="37294-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="37294-513">追加情報</span><span class="sxs-lookup"><span data-stu-id="37294-513">Additional information</span></span>
- <span data-ttu-id="37294-514">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="37294-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="37294-515">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="37294-515">Additional resources</span></span>

| <span data-ttu-id="37294-516">記事</span><span class="sxs-lookup"><span data-stu-id="37294-516">Article</span></span> | <span data-ttu-id="37294-517">説明</span><span class="sxs-lookup"><span data-stu-id="37294-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="37294-518">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="37294-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="37294-519">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="37294-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="37294-520">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="37294-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="37294-521">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="37294-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="37294-522">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="37294-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="37294-523">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="37294-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="37294-524">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="37294-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="37294-525">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="37294-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="37294-526">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="37294-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="37294-527">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="37294-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="37294-528">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="37294-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="37294-529">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="37294-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="37294-530">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="37294-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
