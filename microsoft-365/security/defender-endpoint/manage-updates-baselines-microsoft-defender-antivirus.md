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
ms.date: 05/08/2021
ms.openlocfilehash: 4f2b931018d49affa2d94ddf1a147c4fd2e02085
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302078"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="662d7-104">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="662d7-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="662d7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="662d7-105">**Applies to:**</span></span>

- [<span data-ttu-id="662d7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="662d7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="662d7-107">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="662d7-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="662d7-108">更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="662d7-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="662d7-109">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-109">Security intelligence updates</span></span>
- <span data-ttu-id="662d7-110">製品の更新</span><span class="sxs-lookup"><span data-stu-id="662d7-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="662d7-111">最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。</span><span class="sxs-lookup"><span data-stu-id="662d7-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="662d7-112">パッシブ モードで実行されている場合でも、Microsoft Defender ウイルス対策保護を[更新してください](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="662d7-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="662d7-113">最新のエンジン、プラットフォーム、署名日を確認するには、セキュリティ インテリジェンスの更新プログラム (Microsoft Defender ウイルス対策その他の Microsoft マルウェア対策に関する[ページをご覧ください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="662d7-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="662d7-114">セキュリティ インテリジェンスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-114">Security intelligence updates</span></span>

<span data-ttu-id="662d7-115">Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="662d7-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="662d7-116">更新プログラムは、次の KB 番号の下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="662d7-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="662d7-117">Microsoft Defender ウイルス対策: KB2267602</span><span class="sxs-lookup"><span data-stu-id="662d7-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="662d7-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="662d7-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="662d7-119">クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="662d7-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="662d7-120">セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。</span><span class="sxs-lookup"><span data-stu-id="662d7-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="662d7-121">詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="662d7-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="662d7-122">最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="662d7-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="662d7-123">エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="662d7-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="662d7-124">製品の更新</span><span class="sxs-lookup"><span data-stu-id="662d7-124">Product updates</span></span>

<span data-ttu-id="662d7-125">Microsoft Defender ウイルス対策月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、各リリースと共に主要な機能更新プログラムWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="662d7-126">更新プログラムの配布は、次のいずれかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="662d7-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="662d7-127">Windowsサーバー更新サービス (WSUS)</span><span class="sxs-lookup"><span data-stu-id="662d7-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="662d7-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="662d7-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="662d7-129">Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。</span><span class="sxs-lookup"><span data-stu-id="662d7-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="662d7-130">詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="662d7-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="662d7-131">月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="662d7-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="662d7-132">月次プラットフォームとエンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="662d7-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="662d7-133">プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="662d7-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="662d7-134">すべての更新プログラムに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="662d7-134">All our updates contain</span></span> 
- <span data-ttu-id="662d7-135">パフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="662d7-135">performance improvements;</span></span>
- <span data-ttu-id="662d7-136">サービスの改善。そして</span><span class="sxs-lookup"><span data-stu-id="662d7-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="662d7-137">統合の改善 (クラウド、Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="662d7-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="662d7-138">2021 年 4 月 (プラットフォーム: 4.18.2104.9|エンジン: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="662d7-138">April-2021 (Platform: 4.18.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="662d7-139">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="662d7-140">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="662d7-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="662d7-141">&ensp;プラットフォーム: **4.18.2104.9**</span><span class="sxs-lookup"><span data-stu-id="662d7-141">&ensp;Platform: **4.18.2104.9**</span></span>  
<span data-ttu-id="662d7-142">&ensp;エンジン: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="662d7-143">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="662d7-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-144">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-144">What's new</span></span>
- <span data-ttu-id="662d7-145">その他の動作監視ロジック</span><span class="sxs-lookup"><span data-stu-id="662d7-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="662d7-146">カーネル モードのキーロガー検出の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-147">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-147">Known Issues</span></span>
<span data-ttu-id="662d7-148">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-149">2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="662d7-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="662d7-150">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="662d7-151">&ensp;リリース: **2021** 年 4 月 1 日</span><span class="sxs-lookup"><span data-stu-id="662d7-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="662d7-152">&ensp;プラットフォーム: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="662d7-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="662d7-153">&ensp;エンジン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="662d7-154">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="662d7-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-155">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-155">What's new</span></span>

- <span data-ttu-id="662d7-156">動作監視エンジンの改善</span><span class="sxs-lookup"><span data-stu-id="662d7-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="662d7-157">ネットワークブルートフォース攻撃の軽減策の拡張</span><span class="sxs-lookup"><span data-stu-id="662d7-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="662d7-158">タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="662d7-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-159">Known Issues</span></span>
<span data-ttu-id="662d7-160">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="662d7-161">2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="662d7-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="662d7-162">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="662d7-163">&ensp;リリース: **2021** 年 3 月 9 日</span><span class="sxs-lookup"><span data-stu-id="662d7-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="662d7-164">&ensp;プラットフォーム: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="662d7-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="662d7-165">&ensp;エンジン: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="662d7-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="662d7-166">&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="662d7-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-167">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-167">What's new</span></span>

- <span data-ttu-id="662d7-168">改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="662d7-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="662d7-169">改ざん防止スコープの拡張</span><span class="sxs-lookup"><span data-stu-id="662d7-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-170">Known Issues</span></span>
<span data-ttu-id="662d7-171">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="662d7-172">以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ</span><span class="sxs-lookup"><span data-stu-id="662d7-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="662d7-173">新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="662d7-174">このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="662d7-175">2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="662d7-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="662d7-176">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="662d7-177">&ensp;リリース: **2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="662d7-178">&ensp;プラットフォーム: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="662d7-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="662d7-179">&ensp;エンジン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="662d7-180">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-181">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-181">What's new</span></span>

- <span data-ttu-id="662d7-182">シェルコードの悪用検出の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="662d7-183">資格情報の盗用の試行の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="662d7-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="662d7-184">サービスのスパム対策機能Microsoft Defender ウイルス対策強化</span><span class="sxs-lookup"><span data-stu-id="662d7-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="662d7-185">x64 エミュレーションのARM強化</span><span class="sxs-lookup"><span data-stu-id="662d7-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="662d7-186">修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る</span><span class="sxs-lookup"><span data-stu-id="662d7-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-187">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-187">Known Issues</span></span>
<span data-ttu-id="662d7-188">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="662d7-189">2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="662d7-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="662d7-190">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="662d7-191">&ensp;リリース日: **2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="662d7-192">&ensp;プラットフォーム: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="662d7-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="662d7-193">&ensp;エンジン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="662d7-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="662d7-194">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-195">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-195">What's new</span></span>

- <span data-ttu-id="662d7-196">SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-197">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-197">Known Issues</span></span>
<span data-ttu-id="662d7-198">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="662d7-199">2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="662d7-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="662d7-200">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="662d7-201">&ensp;リリース: **2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="662d7-202">&ensp;プラットフォーム: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="662d7-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="662d7-203">&ensp;エンジン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="662d7-204">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-205">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-205">What's new</span></span>

- <span data-ttu-id="662d7-206">特別な脅威カテゴリの新しい説明</span><span class="sxs-lookup"><span data-stu-id="662d7-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="662d7-207">エミュレーション機能の強化</span><span class="sxs-lookup"><span data-stu-id="662d7-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="662d7-208">ホスト アドレスの許可/ブロック機能の強化</span><span class="sxs-lookup"><span data-stu-id="662d7-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="662d7-209">ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション</span><span class="sxs-lookup"><span data-stu-id="662d7-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-210">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-210">Known Issues</span></span>

<span data-ttu-id="662d7-211">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="662d7-212">2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="662d7-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="662d7-213">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="662d7-214">&ensp;リリース: **2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="662d7-215">&ensp;プラットフォーム: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="662d7-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="662d7-216">&ensp;エンジン: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="662d7-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="662d7-217">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-218">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-218">What's new</span></span>

- <span data-ttu-id="662d7-219">検疫内のファイルを復元するには、管理者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="662d7-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="662d7-220">XML 形式のイベントがサポートされる</span><span class="sxs-lookup"><span data-stu-id="662d7-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="662d7-221">除外マージを無視する CSP のサポート</span><span class="sxs-lookup"><span data-stu-id="662d7-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="662d7-222">次の新しい管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="662d7-222">New management interfaces for:</span></span>
   - <span data-ttu-id="662d7-223">UDP 検査</span><span class="sxs-lookup"><span data-stu-id="662d7-223">UDP Inspection</span></span>
   - <span data-ttu-id="662d7-224">Server 2019 のネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="662d7-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="662d7-225">ネットワーク保護の IP アドレスの除外</span><span class="sxs-lookup"><span data-stu-id="662d7-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="662d7-226">TPM 測定値の可視性の向上</span><span class="sxs-lookup"><span data-stu-id="662d7-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="662d7-227">VBA Officeスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="662d7-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-228">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-228">Known Issues</span></span>

<span data-ttu-id="662d7-229">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="662d7-230">2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="662d7-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="662d7-231">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="662d7-232">&ensp;リリース: **2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="662d7-233">&ensp;プラットフォーム: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="662d7-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="662d7-234">&ensp;エンジン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="662d7-235">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="662d7-236">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-236">What's new</span></span>

- <span data-ttu-id="662d7-237">テレメトリ イベントの追加</span><span class="sxs-lookup"><span data-stu-id="662d7-237">Add more telemetry events</span></span>
- <span data-ttu-id="662d7-238">スキャン イベントの利用統計情報の向上</span><span class="sxs-lookup"><span data-stu-id="662d7-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="662d7-239">メモリ スキャンの動作監視の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="662d7-240">マクロ ストリームのスキャンの改善</span><span class="sxs-lookup"><span data-stu-id="662d7-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="662d7-241">`AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加</span><span class="sxs-lookup"><span data-stu-id="662d7-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="662d7-242">[DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="662d7-243">Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="662d7-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="662d7-244">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-244">Known Issues</span></span>
<span data-ttu-id="662d7-245">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-246">2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="662d7-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="662d7-247">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="662d7-248">&ensp;リリース日: **2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="662d7-249">&ensp;プラットフォーム: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="662d7-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="662d7-250">&ensp;エンジン: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="662d7-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="662d7-251">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-252">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-252">What's new</span></span>

- <span data-ttu-id="662d7-253">BITS の利用統計情報の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="662d7-254">Authenticode コード署名証明書の検証の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-255">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-255">Known Issues</span></span>
<span data-ttu-id="662d7-256">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-257">2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="662d7-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="662d7-258">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="662d7-259">&ensp;リリース日: **2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="662d7-260">&ensp;プラットフォーム: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="662d7-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="662d7-261">&ensp;エンジン: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="662d7-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="662d7-262">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-263">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-263">What's new</span></span>

- <span data-ttu-id="662d7-264">サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="662d7-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="662d7-265">パッシブ モードで積極的なキャッチアップ スキャンをスキップする。</span><span class="sxs-lookup"><span data-stu-id="662d7-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="662d7-266">測定された接続で Defender が更新を許可する</span><span class="sxs-lookup"><span data-stu-id="662d7-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="662d7-267">キャッシュが無効な場合のパフォーマンス調整が修正されました</span><span class="sxs-lookup"><span data-stu-id="662d7-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="662d7-268">レジストリ クエリの修正</span><span class="sxs-lookup"><span data-stu-id="662d7-268">Fixed registry query</span></span> 
- <span data-ttu-id="662d7-269">ADMX でのスキャンタイムランダム化の修正</span><span class="sxs-lookup"><span data-stu-id="662d7-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-270">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-270">Known Issues</span></span>
<span data-ttu-id="662d7-271">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-272">May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="662d7-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="662d7-273">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="662d7-274">&ensp;リリース: **2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="662d7-275">&ensp;プラットフォーム: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="662d7-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="662d7-276">&ensp;エンジン: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="662d7-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="662d7-277">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-278">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-278">What's new</span></span>

- <span data-ttu-id="662d7-279">スキャン イベントのログ記録の改善</span><span class="sxs-lookup"><span data-stu-id="662d7-279">Improved logging for scan events</span></span>
- <span data-ttu-id="662d7-280">ユーザー モードのクラッシュ処理が改善されました。</span><span class="sxs-lookup"><span data-stu-id="662d7-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="662d7-281">タンパープロテクション用のイベント トレースを追加しました</span><span class="sxs-lookup"><span data-stu-id="662d7-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="662d7-282">固定 AMSI サンプル申請</span><span class="sxs-lookup"><span data-stu-id="662d7-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="662d7-283">AMSI クラウドのブロックを修正しました</span><span class="sxs-lookup"><span data-stu-id="662d7-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="662d7-284">固定セキュリティ更新プログラムのインストール ログ</span><span class="sxs-lookup"><span data-stu-id="662d7-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-285">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-285">Known Issues</span></span>
<span data-ttu-id="662d7-286">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-287">April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="662d7-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="662d7-288">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="662d7-289">&ensp;リリース: **2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="662d7-290">&ensp;プラットフォーム: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="662d7-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="662d7-291">&ensp;エンジン: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="662d7-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="662d7-292">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-293">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-293">What's new</span></span>
- <span data-ttu-id="662d7-294">WDfilter の機能強化</span><span class="sxs-lookup"><span data-stu-id="662d7-294">WDfilter improvements</span></span>
- <span data-ttu-id="662d7-295">アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する</span><span class="sxs-lookup"><span data-stu-id="662d7-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="662d7-296">診断データと WMI の固定バージョン情報</span><span class="sxs-lookup"><span data-stu-id="662d7-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="662d7-297">プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました</span><span class="sxs-lookup"><span data-stu-id="662d7-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="662d7-298">ファイルレス脅威保護用の動的 URL intel</span><span class="sxs-lookup"><span data-stu-id="662d7-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="662d7-299">UEFI スキャン機能</span><span class="sxs-lookup"><span data-stu-id="662d7-299">UEFI scan capability</span></span>
- <span data-ttu-id="662d7-300">更新プログラムのログを拡張する</span><span class="sxs-lookup"><span data-stu-id="662d7-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="662d7-301">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-301">Known Issues</span></span>
<span data-ttu-id="662d7-302">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-303">2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="662d7-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="662d7-304">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="662d7-305">&ensp;リリース: **2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="662d7-306">&ensp;プラットフォーム: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="662d7-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="662d7-307">&ensp;エンジン: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="662d7-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="662d7-308">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="662d7-309">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-309">What's new</span></span>

- <span data-ttu-id="662d7-310">MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="662d7-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="662d7-311">診断機能の向上</span><span class="sxs-lookup"><span data-stu-id="662d7-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="662d7-312">セキュリティ インテリジェンス のタイムアウトを減らす (5 分)</span><span class="sxs-lookup"><span data-stu-id="662d7-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="662d7-313">AMSI エンジンの内部ログ機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="662d7-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="662d7-314">プロセスブロックの通知を改善する</span><span class="sxs-lookup"><span data-stu-id="662d7-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="662d7-315">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-315">Known Issues</span></span>
<span data-ttu-id="662d7-316">[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。</span><span class="sxs-lookup"><span data-stu-id="662d7-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="662d7-317">2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="662d7-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="662d7-318">&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="662d7-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="662d7-319">&ensp;リリース: **2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="662d7-320">&ensp;プラットフォーム/クライアント: **-**</span><span class="sxs-lookup"><span data-stu-id="662d7-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="662d7-321">&ensp;エンジン: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="662d7-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="662d7-322">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="662d7-323">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="662d7-324">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-324">Known Issues</span></span>
<span data-ttu-id="662d7-325">既知の問題はありません</span><span class="sxs-lookup"><span data-stu-id="662d7-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-326">2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="662d7-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="662d7-327">セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="662d7-328">リリース: **2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="662d7-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="662d7-329">プラットフォーム/クライアント: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="662d7-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="662d7-330">エンジン: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="662d7-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="662d7-331">&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**</span><span class="sxs-lookup"><span data-stu-id="662d7-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="662d7-332">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-332">What's new</span></span>

- <span data-ttu-id="662d7-333">WS2016 の固定 BSOD とExchange</span><span class="sxs-lookup"><span data-stu-id="662d7-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="662d7-334">TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする</span><span class="sxs-lookup"><span data-stu-id="662d7-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="662d7-335">プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="662d7-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="662d7-336">緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="662d7-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="662d7-337">Fix 4.18.1911.3 ハング</span><span class="sxs-lookup"><span data-stu-id="662d7-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="662d7-338">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-338">Known Issues</span></span>

<span data-ttu-id="662d7-339">[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="662d7-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="662d7-340">影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="662d7-341">この更新プログラムは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="662d7-341">This update is:</span></span>
> - <span data-ttu-id="662d7-342">SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="662d7-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="662d7-343">ハングの問題があるシステムの再起動フラグがあります。</span><span class="sxs-lookup"><span data-stu-id="662d7-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="662d7-344">は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="662d7-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="662d7-345">は、再起動要件による更新プログラムとして分類されます。そして</span><span class="sxs-lookup"><span data-stu-id="662d7-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="662d7-346">は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="662d7-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="662d7-347">2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="662d7-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="662d7-348">セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="662d7-349">リリース日: **2019 年 12** 月 7 日</span><span class="sxs-lookup"><span data-stu-id="662d7-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="662d7-350">プラットフォーム: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="662d7-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="662d7-351">エンジン: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="662d7-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="662d7-352">サポート フェーズ: **サポートなし**</span><span class="sxs-lookup"><span data-stu-id="662d7-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="662d7-353">新機能</span><span class="sxs-lookup"><span data-stu-id="662d7-353">What's new</span></span>

- <span data-ttu-id="662d7-354">固定 MpCmdRun トレース レベル</span><span class="sxs-lookup"><span data-stu-id="662d7-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="662d7-355">WDFilter のバージョン情報を修正しました</span><span class="sxs-lookup"><span data-stu-id="662d7-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="662d7-356">通知の改善 (PUA)</span><span class="sxs-lookup"><span data-stu-id="662d7-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="662d7-357">MRT ログをサポート ファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="662d7-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="662d7-358">既知の問題</span><span class="sxs-lookup"><span data-stu-id="662d7-358">Known Issues</span></span>
<span data-ttu-id="662d7-359">この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="662d7-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="662d7-360">Microsoft Defender ウイルス対策サポート</span><span class="sxs-lookup"><span data-stu-id="662d7-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="662d7-361">プラットフォームとエンジンの更新プログラムは、毎月提供されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="662d7-362">完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="662d7-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="662d7-363">サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。</span><span class="sxs-lookup"><span data-stu-id="662d7-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="662d7-364">**セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。</span><span class="sxs-lookup"><span data-stu-id="662d7-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="662d7-365">**テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。</span><span class="sxs-lookup"><span data-stu-id="662d7-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="662d7-366">N-2 より古いプラットフォーム バージョンはサポートされなくなりました。\*</span><span class="sxs-lookup"><span data-stu-id="662d7-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="662d7-367">\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="662d7-368">テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="662d7-369">サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (\*)へのアップグレードを求める要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="662d7-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="662d7-370">プラットフォームのバージョンは、Windows 10リリースに含まれています</span><span class="sxs-lookup"><span data-stu-id="662d7-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="662d7-371">次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。</span><span class="sxs-lookup"><span data-stu-id="662d7-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="662d7-372">Windows 10リリース</span><span class="sxs-lookup"><span data-stu-id="662d7-372">Windows 10 release</span></span>  |<span data-ttu-id="662d7-373">プラットフォームのバージョン</span><span class="sxs-lookup"><span data-stu-id="662d7-373">Platform version</span></span>  |<span data-ttu-id="662d7-374">エンジンのバージョン</span><span class="sxs-lookup"><span data-stu-id="662d7-374">Engine version</span></span> |<span data-ttu-id="662d7-375">サポート フェーズ</span><span class="sxs-lookup"><span data-stu-id="662d7-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="662d7-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="662d7-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="662d7-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="662d7-377">4.18.1909.6</span></span> |<span data-ttu-id="662d7-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="662d7-378">1.1.17000.2</span></span> | <span data-ttu-id="662d7-379">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="662d7-380">1909  (19H2)</span></span> |<span data-ttu-id="662d7-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="662d7-381">4.18.1902.5</span></span> |<span data-ttu-id="662d7-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="662d7-382">1.1.16700.3</span></span> | <span data-ttu-id="662d7-383">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="662d7-384">1903  (19H1)</span></span> |<span data-ttu-id="662d7-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="662d7-385">4.18.1902.5</span></span> |<span data-ttu-id="662d7-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="662d7-386">1.1.15600.4</span></span> | <span data-ttu-id="662d7-387">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="662d7-388">1809  (RS5)</span></span> |<span data-ttu-id="662d7-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="662d7-389">4.18.1807.18075</span></span> |<span data-ttu-id="662d7-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="662d7-390">1.1.15000.2</span></span> | <span data-ttu-id="662d7-391">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="662d7-392">1803  (RS4)</span></span> |<span data-ttu-id="662d7-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="662d7-393">4.13.17134.1</span></span> |<span data-ttu-id="662d7-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="662d7-394">1.1.14600.4</span></span> | <span data-ttu-id="662d7-395">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="662d7-396">1709  (RS3)</span></span> |<span data-ttu-id="662d7-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="662d7-397">4.12.16299.15</span></span> |<span data-ttu-id="662d7-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="662d7-398">1.1.14104.0</span></span> | <span data-ttu-id="662d7-399">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="662d7-400">1703  (RS2)</span></span> |<span data-ttu-id="662d7-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="662d7-401">4.11.15603.2</span></span> |<span data-ttu-id="662d7-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="662d7-402">1.1.13504.0</span></span> | <span data-ttu-id="662d7-403">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="662d7-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="662d7-404">1607 (RS1)</span></span> |<span data-ttu-id="662d7-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="662d7-405">4.10.14393.3683</span></span> |<span data-ttu-id="662d7-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="662d7-406">1.1.12805.0</span></span> | <span data-ttu-id="662d7-407">テクニカル アップグレード のサポート (のみ)</span><span class="sxs-lookup"><span data-stu-id="662d7-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="662d7-408">リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="662d7-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="662d7-409">展開イメージのサービスと管理 (DISM) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="662d7-410">Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="662d7-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="662d7-411">OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="662d7-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="662d7-412">詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="662d7-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="662d7-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="662d7-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="662d7-414">&ensp;パッケージのバージョン: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="662d7-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="662d7-415">&ensp;プラットフォーム のバージョン: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="662d7-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="662d7-416">&ensp;エンジンのバージョン: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="662d7-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="662d7-417">&ensp;署名バージョン: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-418">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-418">Fixes</span></span>
- <span data-ttu-id="662d7-419">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-420">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-420">Additional information</span></span>
- <span data-ttu-id="662d7-421">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="662d7-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="662d7-423">&ensp;パッケージのバージョン: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="662d7-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="662d7-424">&ensp;プラットフォーム のバージョン: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="662d7-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="662d7-425">&ensp;エンジンのバージョン: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="662d7-426">&ensp;署名バージョン: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-427">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-427">Fixes</span></span>
- <span data-ttu-id="662d7-428">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-429">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-429">Additional information</span></span>
- <span data-ttu-id="662d7-430">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="662d7-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="662d7-432">&ensp;パッケージのバージョン: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="662d7-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="662d7-433">&ensp;プラットフォーム バージョン: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="662d7-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="662d7-434">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="662d7-435">&ensp;署名バージョン: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-436">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-436">Fixes</span></span>
- <span data-ttu-id="662d7-437">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-438">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-438">Additional information</span></span>
- <span data-ttu-id="662d7-439">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="662d7-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="662d7-441">&ensp;パッケージのバージョン: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="662d7-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="662d7-442">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="662d7-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="662d7-443">&ensp;エンジンのバージョン: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="662d7-444">&ensp;署名バージョン: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-445">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-445">Fixes</span></span>
- <span data-ttu-id="662d7-446">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-447">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-447">Additional information</span></span>
- <span data-ttu-id="662d7-448">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="662d7-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="662d7-450">&ensp;パッケージ のバージョン: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="662d7-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="662d7-451">&ensp;プラットフォーム バージョン: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="662d7-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="662d7-452">&ensp;エンジンのバージョン: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="662d7-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="662d7-453">&ensp;署名バージョン: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-454">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-454">Fixes</span></span>
- <span data-ttu-id="662d7-455">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-456">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-456">Additional information</span></span>
- <span data-ttu-id="662d7-457">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="662d7-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="662d7-459">&ensp;パッケージのバージョン: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="662d7-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="662d7-460">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="662d7-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="662d7-461">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="662d7-462">&ensp;署名バージョン: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-463">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-463">Fixes</span></span>
- <span data-ttu-id="662d7-464">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-465">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-465">Additional information</span></span>
- <span data-ttu-id="662d7-466">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="662d7-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="662d7-468">&ensp;パッケージ のバージョン: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="662d7-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="662d7-469">&ensp;プラットフォーム のバージョン: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="662d7-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="662d7-470">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="662d7-471">&ensp;署名バージョン: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-472">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-472">Fixes</span></span>
- <span data-ttu-id="662d7-473">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-474">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-474">Additional information</span></span>
- <span data-ttu-id="662d7-475">更新されたMicrosoft Defender ウイルス対策署名</span><span class="sxs-lookup"><span data-stu-id="662d7-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="662d7-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="662d7-477">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="662d7-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="662d7-478">&ensp;プラットフォーム バージョン: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="662d7-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="662d7-479">&ensp;エンジンのバージョン: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="662d7-480">&ensp;署名バージョン: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-481">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-481">Fixes</span></span>
- <span data-ttu-id="662d7-482">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-483">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-483">Additional information</span></span>
- <span data-ttu-id="662d7-484">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="662d7-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="662d7-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="662d7-486">&ensp;パッケージ のバージョン: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="662d7-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="662d7-487">&ensp;プラットフォーム バージョン: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="662d7-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="662d7-488">&ensp;エンジンのバージョン: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="662d7-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="662d7-489">&ensp;署名バージョン: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="662d7-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="662d7-490">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-490">Fixes</span></span>
- <span data-ttu-id="662d7-491">なし</span><span class="sxs-lookup"><span data-stu-id="662d7-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="662d7-492">追加情報</span><span class="sxs-lookup"><span data-stu-id="662d7-492">Additional information</span></span>
- <span data-ttu-id="662d7-493">RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="662d7-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="662d7-494">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="662d7-494">Additional resources</span></span>

| <span data-ttu-id="662d7-495">記事</span><span class="sxs-lookup"><span data-stu-id="662d7-495">Article</span></span> | <span data-ttu-id="662d7-496">説明</span><span class="sxs-lookup"><span data-stu-id="662d7-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="662d7-497">Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム</span><span class="sxs-lookup"><span data-stu-id="662d7-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="662d7-498">OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="662d7-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="662d7-499">Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="662d7-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="662d7-500">保護更新プログラムのダウンロードと適用方法を管理する</span><span class="sxs-lookup"><span data-stu-id="662d7-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="662d7-501">保護更新プログラムは、多くのソースを介して配信できます。</span><span class="sxs-lookup"><span data-stu-id="662d7-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="662d7-502">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="662d7-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="662d7-503">保護更新プログラムをダウンロードするスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="662d7-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="662d7-504">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="662d7-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="662d7-505">エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="662d7-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="662d7-506">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="662d7-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="662d7-507">保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。</span><span class="sxs-lookup"><span data-stu-id="662d7-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="662d7-508">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="662d7-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="662d7-509">モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="662d7-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
