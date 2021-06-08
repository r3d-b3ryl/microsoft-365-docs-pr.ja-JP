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
ms.date: 06/07/2021
ms.openlocfilehash: 33170d4706ed53f4de687c34806bb0492a08836e
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809109"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="b538b-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="b538b-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="b538b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b538b-105">**Applies to:**</span></span>

- [<span data-ttu-id="b538b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b538b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="b538b-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="b538b-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="b538b-108">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="b538b-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="b538b-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-109">Security intelligence updates</span></span>
- <span data-ttu-id="b538b-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="b538b-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b538b-111">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="b538b-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="b538b-112">パッシブ モードで実行されている場合でも、Microsoft Defender ウイルス対策保護を[更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="b538b-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="b538b-113">最新のエンジン、プラットフォーム、署名日を確認するには、セキュリティ インテリジェンスの更新プログラム (Microsoft Defender ウイルス対策その他の Microsoft マルウェア対策に関する[ページをご覧ください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="b538b-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="b538b-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-114">Security intelligence updates</span></span>

<span data-ttu-id="b538b-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="b538b-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="b538b-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="b538b-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="b538b-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="b538b-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="b538b-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="b538b-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="b538b-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b538b-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="b538b-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="b538b-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="b538b-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b538b-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="b538b-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="b538b-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="b538b-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="b538b-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="b538b-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="b538b-124">Product updates</span></span>

<span data-ttu-id="b538b-125">Microsoft Defender ウイルス対策月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、各リリースと共に主要な機能更新プログラムWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="b538b-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="b538b-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="b538b-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="b538b-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="b538b-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b538b-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="b538b-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="b538b-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="b538b-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b538b-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="b538b-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b538b-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="b538b-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="b538b-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="b538b-133">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="b538b-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="b538b-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="b538b-134">All our updates contain</span></span> 
- <span data-ttu-id="b538b-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="b538b-135">performance improvements;</span></span>
- <span data-ttu-id="b538b-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="b538b-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="b538b-137">統合の改善 (Cloud、Microsoft 365 [Defender)。](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="b538b-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="b538b-138">May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="b538b-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="b538b-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="b538b-140">&ensp;リリース: **2021 年 6 月 4 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="b538b-141">&ensp;プラットフォーム: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="b538b-142">&ensp;エンジン: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="b538b-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b538b-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-144">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-144">What's new</span></span>
- <span data-ttu-id="b538b-145">動作監視 [の改善](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="b538b-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="b538b-146">固定 [ネットワーク保護通知](network-protection.md) フィルター機能</span><span class="sxs-lookup"><span data-stu-id="b538b-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-147">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-147">Known Issues</span></span>
<span data-ttu-id="b538b-148">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b538b-149">2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="b538b-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="b538b-150">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="b538b-151">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="b538b-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b538b-152">&ensp;プラットフォーム: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="b538b-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="b538b-153">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="b538b-154">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b538b-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-155">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-155">What's new</span></span>
- <span data-ttu-id="b538b-156">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="b538b-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="b538b-157">カーネル モードのキーロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-158">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-158">Known Issues</span></span>
<span data-ttu-id="b538b-159">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b538b-160">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="b538b-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="b538b-161">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="b538b-162">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="b538b-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b538b-163">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="b538b-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="b538b-164">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="b538b-165">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="b538b-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-166">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-166">What's new</span></span>

- <span data-ttu-id="b538b-167">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="b538b-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="b538b-168">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="b538b-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="b538b-169">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="b538b-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-170">Known Issues</span></span>
<span data-ttu-id="b538b-171">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="b538b-172">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="b538b-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="b538b-173">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="b538b-174">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="b538b-175">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="b538b-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="b538b-176">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="b538b-177">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="b538b-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="b538b-178">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="b538b-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="b538b-179">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="b538b-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="b538b-180">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-181">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-181">What's new</span></span>

- <span data-ttu-id="b538b-182">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b538b-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="b538b-183">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="b538b-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-184">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-184">Known Issues</span></span>
<span data-ttu-id="b538b-185">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b538b-186">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="b538b-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="b538b-187">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b538b-188">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="b538b-189">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="b538b-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="b538b-190">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="b538b-191">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-192">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-192">What's new</span></span>

- <span data-ttu-id="b538b-193">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="b538b-194">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="b538b-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="b538b-195">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="b538b-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="b538b-196">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="b538b-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="b538b-197">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="b538b-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-198">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-198">Known Issues</span></span>
<span data-ttu-id="b538b-199">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b538b-200">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="b538b-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="b538b-201">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b538b-202">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="b538b-203">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="b538b-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="b538b-204">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="b538b-205">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-206">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-206">What's new</span></span>

- <span data-ttu-id="b538b-207">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-208">Known Issues</span></span>
<span data-ttu-id="b538b-209">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b538b-210">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="b538b-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="b538b-211">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="b538b-212">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="b538b-213">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="b538b-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="b538b-214">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="b538b-215">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-216">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-216">What's new</span></span>

- <span data-ttu-id="b538b-217">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="b538b-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="b538b-218">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="b538b-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="b538b-219">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="b538b-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="b538b-220">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="b538b-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-221">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-221">Known Issues</span></span>

<span data-ttu-id="b538b-222">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b538b-223">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="b538b-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="b538b-224">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="b538b-225">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="b538b-226">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b538b-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="b538b-227">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="b538b-228">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-229">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-229">What's new</span></span>

- <span data-ttu-id="b538b-230">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="b538b-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="b538b-231">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="b538b-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="b538b-232">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="b538b-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="b538b-233">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b538b-233">New management interfaces for:</span></span>
   - <span data-ttu-id="b538b-234">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="b538b-234">UDP Inspection</span></span>
   - <span data-ttu-id="b538b-235">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="b538b-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="b538b-236">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="b538b-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="b538b-237">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="b538b-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="b538b-238">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="b538b-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-239">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-239">Known Issues</span></span>

<span data-ttu-id="b538b-240">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="b538b-241">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="b538b-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="b538b-242">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="b538b-243">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="b538b-244">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="b538b-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="b538b-245">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="b538b-246">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="b538b-247">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-247">What's new</span></span>

- <span data-ttu-id="b538b-248">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="b538b-248">Add more telemetry events</span></span>
- <span data-ttu-id="b538b-249">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="b538b-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="b538b-250">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="b538b-251">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="b538b-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="b538b-252">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="b538b-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="b538b-253">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="b538b-254">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="b538b-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="b538b-255">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-255">Known Issues</span></span>
<span data-ttu-id="b538b-256">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-257">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="b538b-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="b538b-258">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="b538b-259">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="b538b-260">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="b538b-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="b538b-261">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="b538b-262">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-263">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-263">What's new</span></span>

- <span data-ttu-id="b538b-264">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="b538b-265">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-266">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-266">Known Issues</span></span>
<span data-ttu-id="b538b-267">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-268">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="b538b-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="b538b-269">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="b538b-270">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="b538b-271">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="b538b-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="b538b-272">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="b538b-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="b538b-273">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-274">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-274">What's new</span></span>

- <span data-ttu-id="b538b-275">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="b538b-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="b538b-276">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="b538b-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="b538b-277">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="b538b-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="b538b-278">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="b538b-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="b538b-279">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="b538b-279">Fixed registry query</span></span> 
- <span data-ttu-id="b538b-280">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="b538b-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-281">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-281">Known Issues</span></span>
<span data-ttu-id="b538b-282">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-283">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="b538b-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="b538b-284">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="b538b-285">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="b538b-286">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="b538b-287">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="b538b-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="b538b-288">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-289">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-289">What's new</span></span>

- <span data-ttu-id="b538b-290">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="b538b-290">Improved logging for scan events</span></span>
- <span data-ttu-id="b538b-291">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="b538b-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="b538b-292">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="b538b-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="b538b-293">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="b538b-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="b538b-294">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="b538b-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="b538b-295">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="b538b-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-296">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-296">Known Issues</span></span>
<span data-ttu-id="b538b-297">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-298">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="b538b-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="b538b-299">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="b538b-300">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="b538b-301">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="b538b-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="b538b-302">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="b538b-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="b538b-303">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-304">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-304">What's new</span></span>
- <span data-ttu-id="b538b-305">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="b538b-305">WDfilter improvements</span></span>
- <span data-ttu-id="b538b-306">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="b538b-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="b538b-307">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="b538b-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="b538b-308">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="b538b-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="b538b-309">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="b538b-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="b538b-310">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="b538b-310">UEFI scan capability</span></span>
- <span data-ttu-id="b538b-311">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="b538b-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="b538b-312">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-312">Known Issues</span></span>
<span data-ttu-id="b538b-313">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-314">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="b538b-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="b538b-315">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="b538b-316">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="b538b-317">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="b538b-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="b538b-318">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="b538b-319">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b538b-320">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-320">What's new</span></span>

- <span data-ttu-id="b538b-321">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b538b-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="b538b-322">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="b538b-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="b538b-323">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="b538b-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="b538b-324">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="b538b-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="b538b-325">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="b538b-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b538b-326">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-326">Known Issues</span></span>
<span data-ttu-id="b538b-327">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="b538b-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="b538b-328">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="b538b-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="b538b-329">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="b538b-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="b538b-330">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="b538b-331">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="b538b-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="b538b-332">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="b538b-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="b538b-333">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b538b-334">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="b538b-335">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-335">Known Issues</span></span>
<span data-ttu-id="b538b-336">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="b538b-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-337">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="b538b-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="b538b-338">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="b538b-339">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="b538b-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="b538b-340">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="b538b-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="b538b-341">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="b538b-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="b538b-342">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="b538b-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b538b-343">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-343">What's new</span></span>

- <span data-ttu-id="b538b-344">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="b538b-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="b538b-345">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="b538b-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="b538b-346">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="b538b-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="b538b-347">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b538b-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="b538b-348">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="b538b-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b538b-349">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-349">Known Issues</span></span>

<span data-ttu-id="b538b-350">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b538b-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="b538b-351">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="b538b-352">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="b538b-352">This update is:</span></span>
> - <span data-ttu-id="b538b-353">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="b538b-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="b538b-354">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="b538b-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="b538b-355">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="b538b-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="b538b-356">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="b538b-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="b538b-357">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="b538b-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b538b-358">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="b538b-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="b538b-359">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="b538b-360">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="b538b-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="b538b-361">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="b538b-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="b538b-362">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="b538b-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="b538b-363">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="b538b-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="b538b-364">新機能</span><span class="sxs-lookup"><span data-stu-id="b538b-364">What's new</span></span>

- <span data-ttu-id="b538b-365">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="b538b-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="b538b-366">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="b538b-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="b538b-367">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="b538b-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="b538b-368">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="b538b-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b538b-369">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b538b-369">Known Issues</span></span>
<span data-ttu-id="b538b-370">この更新プログラムをインストールすると、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.18.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b538b-370">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="b538b-371">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="b538b-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="b538b-372">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="b538b-373">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="b538b-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="b538b-374">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="b538b-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="b538b-375">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="b538b-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="b538b-376">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="b538b-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="b538b-377">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="b538b-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="b538b-378">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="b538b-379">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="b538b-380">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b538b-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="b538b-381">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="b538b-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="b538b-382">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="b538b-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="b538b-383">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="b538b-383">Windows 10 release</span></span>  |<span data-ttu-id="b538b-384">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="b538b-384">Platform version</span></span>  |<span data-ttu-id="b538b-385">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="b538b-385">Engine version</span></span> |<span data-ttu-id="b538b-386">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="b538b-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b538b-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="b538b-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="b538b-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="b538b-388">4.18.1909.6</span></span> |<span data-ttu-id="b538b-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="b538b-389">1.1.17000.2</span></span> | <span data-ttu-id="b538b-390">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="b538b-391">1909  (19H2)</span></span> |<span data-ttu-id="b538b-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b538b-392">4.18.1902.5</span></span> |<span data-ttu-id="b538b-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="b538b-393">1.1.16700.3</span></span> | <span data-ttu-id="b538b-394">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="b538b-395">1903  (19H1)</span></span> |<span data-ttu-id="b538b-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b538b-396">4.18.1902.5</span></span> |<span data-ttu-id="b538b-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="b538b-397">1.1.15600.4</span></span> | <span data-ttu-id="b538b-398">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="b538b-399">1809  (RS5)</span></span> |<span data-ttu-id="b538b-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="b538b-400">4.18.1807.18075</span></span> |<span data-ttu-id="b538b-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="b538b-401">1.1.15000.2</span></span> | <span data-ttu-id="b538b-402">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="b538b-403">1803  (RS4)</span></span> |<span data-ttu-id="b538b-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="b538b-404">4.13.17134.1</span></span> |<span data-ttu-id="b538b-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="b538b-405">1.1.14600.4</span></span> | <span data-ttu-id="b538b-406">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="b538b-407">1709  (RS3)</span></span> |<span data-ttu-id="b538b-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="b538b-408">4.12.16299.15</span></span> |<span data-ttu-id="b538b-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="b538b-409">1.1.14104.0</span></span> | <span data-ttu-id="b538b-410">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="b538b-411">1703  (RS2)</span></span> |<span data-ttu-id="b538b-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="b538b-412">4.11.15603.2</span></span> |<span data-ttu-id="b538b-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="b538b-413">1.1.13504.0</span></span> | <span data-ttu-id="b538b-414">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b538b-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="b538b-415">1607 (RS1)</span></span> |<span data-ttu-id="b538b-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="b538b-416">4.10.14393.3683</span></span> |<span data-ttu-id="b538b-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="b538b-417">1.1.12805.0</span></span> | <span data-ttu-id="b538b-418">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="b538b-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="b538b-419">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="b538b-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="b538b-420">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="b538b-421">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b538b-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="b538b-422">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b538b-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="b538b-423">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="b538b-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="b538b-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="b538b-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="b538b-425">&ensp;パッケージ のバージョン: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="b538b-426">&ensp;プラットフォーム のバージョン: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="b538b-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="b538b-427">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b538b-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b538b-428">&ensp;署名バージョン: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-429">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-429">Fixes</span></span>
- <span data-ttu-id="b538b-430">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-431">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-431">Additional information</span></span>
- <span data-ttu-id="b538b-432">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="b538b-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="b538b-434">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="b538b-435">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="b538b-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="b538b-436">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b538b-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b538b-437">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-438">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-438">Fixes</span></span>
- <span data-ttu-id="b538b-439">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-440">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-440">Additional information</span></span>
- <span data-ttu-id="b538b-441">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="b538b-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="b538b-443">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="b538b-444">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="b538b-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="b538b-445">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="b538b-446">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-447">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-447">Fixes</span></span>
- <span data-ttu-id="b538b-448">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-449">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-449">Additional information</span></span>
- <span data-ttu-id="b538b-450">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="b538b-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="b538b-452">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="b538b-453">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="b538b-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="b538b-454">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b538b-455">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-456">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-456">Fixes</span></span>
- <span data-ttu-id="b538b-457">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-458">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-458">Additional information</span></span>
- <span data-ttu-id="b538b-459">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="b538b-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="b538b-461">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="b538b-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="b538b-462">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b538b-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b538b-463">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b538b-464">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-465">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-465">Fixes</span></span>
- <span data-ttu-id="b538b-466">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-467">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-467">Additional information</span></span>
- <span data-ttu-id="b538b-468">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="b538b-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="b538b-470">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="b538b-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="b538b-471">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b538b-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b538b-472">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b538b-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="b538b-473">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-474">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-474">Fixes</span></span>
- <span data-ttu-id="b538b-475">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-476">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-476">Additional information</span></span>
- <span data-ttu-id="b538b-477">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="b538b-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="b538b-479">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="b538b-480">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b538b-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b538b-481">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b538b-482">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-483">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-483">Fixes</span></span>
- <span data-ttu-id="b538b-484">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-485">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-485">Additional information</span></span>
- <span data-ttu-id="b538b-486">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="b538b-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="b538b-488">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="b538b-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="b538b-489">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b538b-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b538b-490">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b538b-491">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-492">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-492">Fixes</span></span>
- <span data-ttu-id="b538b-493">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-494">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-494">Additional information</span></span>
- <span data-ttu-id="b538b-495">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="b538b-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="b538b-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="b538b-497">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b538b-498">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b538b-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="b538b-499">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b538b-500">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-501">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-501">Fixes</span></span>
- <span data-ttu-id="b538b-502">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-503">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-503">Additional information</span></span>
- <span data-ttu-id="b538b-504">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b538b-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="b538b-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="b538b-506">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b538b-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b538b-507">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="b538b-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="b538b-508">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b538b-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="b538b-509">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="b538b-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b538b-510">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-510">Fixes</span></span>
- <span data-ttu-id="b538b-511">なし</span><span class="sxs-lookup"><span data-stu-id="b538b-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b538b-512">追加情報</span><span class="sxs-lookup"><span data-stu-id="b538b-512">Additional information</span></span>
- <span data-ttu-id="b538b-513">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b538b-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="b538b-514">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="b538b-514">Additional resources</span></span>

| <span data-ttu-id="b538b-515">記事</span><span class="sxs-lookup"><span data-stu-id="b538b-515">Article</span></span> | <span data-ttu-id="b538b-516">説明</span><span class="sxs-lookup"><span data-stu-id="b538b-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="b538b-517">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b538b-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="b538b-518">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="b538b-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="b538b-519">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="b538b-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="b538b-520">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="b538b-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b538b-521">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="b538b-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="b538b-522">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="b538b-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="b538b-523">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b538b-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="b538b-524">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b538b-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="b538b-525">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b538b-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="b538b-526">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b538b-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b538b-527">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="b538b-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="b538b-528">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="b538b-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="b538b-529">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b538b-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
