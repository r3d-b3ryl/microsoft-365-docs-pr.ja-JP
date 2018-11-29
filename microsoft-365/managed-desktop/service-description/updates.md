---
title: Microsoft マネージド デスクトップでの更新プログラムの処理方法
description: 管理されたデスクトップのマイクロソフトの最新の状態を保持することは、速度と安定性のバランスです。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869105"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="e3ef8-104">Microsoft マネージド デスクトップでの更新プログラムの処理方法</span><span class="sxs-lookup"><span data-stu-id="e3ef8-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="e3ef8-p101">Microsoft 管理されたデスクトップは、最新のクラウド ・ ベースのインフラストラクチャをすべてのデバイスを接続します。速度と安定性のバランスは、Windows、Office、ドライバー、ファームウェア、および Microsoft ストア ビジネス アプリケーションの更新プログラムを最新に保ちます。OS を確認するのには展開リングが使用され、ポリシーを安全に公開します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-rings"></a><span data-ttu-id="e3ef8-108">リングを更新します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-108">Update rings</span></span>

<span data-ttu-id="e3ef8-109">Microsoft 管理されたデスクトップでは、更新プログラムを管理するのには Azure AD の 4 つのグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="e3ef8-110">テスト: テスト リングだけは、お客様のテナントに加えられた変更のテストおよび検証。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-110">Test: The test ring is only designed for test and validation of changes made in the customer tenant.</span></span>  
- <span data-ttu-id="e3ef8-111">1: まずは、事前にソフトウェアをインストールし、いくつかのプレリリース版更新プログラムの対象になるには、限られた技術の豊富なユーザーに事前のテストのリングです。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-111">First: First is intended to be an early test ring with limited tech savvy users that are willing to install software early and be subject to some pre-release updates.</span></span>
- <span data-ttu-id="e3ef8-p102">高速: 高速リングは、大規模な一連のユーザーが予想されるが。 このリングの目標は、更新やソフトウェア配信の簡単なペースでセキュリティで保護されたデバイスを保持すること。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p102">Fast: The fast ring is where we would expect a large set of users.  The goal for this ring is to keep devices updated and secure with a quick pace of software delivery.</span></span>  
- <span data-ttu-id="e3ef8-p103">広範な: 低速のリングは、品質と機能の更新プログラムからのバランスのとれた控えめなロールです。 品質の更新プログラムはまだ高速に配信のペースですが、すぐにします。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p103">Broad: The slow ring is a balanced conservative roll out of quality and feature updates.  Quality updates are still delivered at a fast pace, but not immediately.</span></span> 

<span data-ttu-id="e3ef8-116">リング システムの更新プログラムは品質として分類されるか、機能の更新プログラム。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-116">The updates in the ring system are categorized as quality, or feature updates:</span></span>
- <span data-ttu-id="e3ef8-p104">品質の更新プログラムには、セキュリティの重要なおよびドライバーの更新プログラムが含まれます。 これらは、通常の毎月の更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p104">Quality updates include security, critical, and driver updates.  These are usually monthly updates.</span></span> 
- <span data-ttu-id="e3ef8-119">機能の更新には、だけでなくセキュリティと品質のリビジョンも重要な機能の追加や変更が含まれています。半年ごとに解放されます。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-119">Feature updates contain not only security and quality revisions, but also significant feature additions and changes; they are released semi-annually.</span></span> 

<span data-ttu-id="e3ef8-120">リングの上位変換のしくみ。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-120">How ring promotion works:</span></span>
- <span data-ttu-id="e3ef8-121">Microsoft 管理されたデスクトップでは、以下に指定したスケジュールの設定に基づいて新しい機能や品質の更新を展開します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-121">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="e3ef8-122">、展開中に Microsoft の管理されたデスクトップの監視の障害やその他の停止を (を使用して遠隔測定の信号とエンド ・ ユーザー ・ サポート ・ システム) です。いずれかが検出された場合はすべての現在および将来のリングへの展開は、すぐに一時停止されました。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-122">During deployment, Microsoft Managed Desktop monitors for signs of failure or other disruption (via telemetry signals and our end-user support system); if any are detected, then the deployment to all current and future rings is immediately paused.</span></span>
    - <span data-ttu-id="e3ef8-123">例: 最初の呼び出し音に品質の更新プログラムの展開中に問題が見つかった場合、最初に、かつ迅速、そして広範なすべてが一時停止される問題が解決されるまで。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-123">Example: if an issue is discovered while deploying a quality update to the First ring, then First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="e3ef8-124">Microsoft デスクトップ IT 管理者の管理ポータルにチケットを送信することにより互換性の問題を報告することがあります。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="e3ef8-p105">機能と品質の更新プログラムが個別に一時停止します。 一時停止 35 日を既定で有効にされてが削減または問題を改善するかどうかによって拡張します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p105">Feature and quality updates are paused independently.  Pause is in effect for 35 days by default but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="e3ef8-127">リングが使用されていないが、以下のスケジュールに従って配置を再開します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-127">Once the rings are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="e3ef8-128">このプロモーション プロセス タイムラインがそれぞれ異なりますが、機能と品質の両方の更新プログラムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-128">This promotion process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="e3ef8-129">リングと遅延の設定</span><span class="sxs-lookup"><span data-stu-id="e3ef8-129">Rings and deferral settings</span></span></th></tr>
<tr><th><span data-ttu-id="e3ef8-130">更新の種類</span><span class="sxs-lookup"><span data-stu-id="e3ef8-130">Update type</span></span></th><th><span data-ttu-id="e3ef8-131">テスト リング</span><span class="sxs-lookup"><span data-stu-id="e3ef8-131">Test ring</span></span></th><th><span data-ttu-id="e3ef8-132">まずは</span><span class="sxs-lookup"><span data-stu-id="e3ef8-132">First</span></span></th><th><span data-ttu-id="e3ef8-133">高速します。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-133">Fast</span></span></th><th><span data-ttu-id="e3ef8-134">広範です</span><span class="sxs-lookup"><span data-stu-id="e3ef8-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="e3ef8-135">オペレーティング ・ システムの品質の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3ef8-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="e3ef8-136">0 日</span><span class="sxs-lookup"><span data-stu-id="e3ef8-136">0 days</span></span></td><td><span data-ttu-id="e3ef8-137">0 日</span><span class="sxs-lookup"><span data-stu-id="e3ef8-137">0 days</span></span></td><td><span data-ttu-id="e3ef8-138">1 日</span><span class="sxs-lookup"><span data-stu-id="e3ef8-138">1 day</span></span></td><td><span data-ttu-id="e3ef8-139">5 日</span><span class="sxs-lookup"><span data-stu-id="e3ef8-139">5 days</span></span></td></tr>
<tr><td><span data-ttu-id="e3ef8-140">オペレーティング システムの機能の更新</span><span class="sxs-lookup"><span data-stu-id="e3ef8-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="e3ef8-141">半年を 1 のチャネル (ターゲット) + 0 日</span><span class="sxs-lookup"><span data-stu-id="e3ef8-141">Semi-annual channel (targeted) + 0 days</span></span></td><td><span data-ttu-id="e3ef8-142">半年を 1 のチャネル (ターゲット) + 30 日間</span><span class="sxs-lookup"><span data-stu-id="e3ef8-142">Semi-annual channel (targeted) + 30 days</span></span></td><td><span data-ttu-id="e3ef8-143">半年を 1 のチャネル (ターゲット) + 60 日間</span><span class="sxs-lookup"><span data-stu-id="e3ef8-143">Semi-annual channel (targeted) + 60 days</span></span></td><td><span data-ttu-id="e3ef8-144">半年を 1 チャンネル + 30 日間</span><span class="sxs-lookup"><span data-stu-id="e3ef8-144">Semi-annual channel + 30 days</span></span></td></tr>
<tr><td><span data-ttu-id="e3ef8-145">ドライバーやファームウェア</span><span class="sxs-lookup"><span data-stu-id="e3ef8-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="e3ef8-146">品質の更新プログラムのスケジュールをに従って、</span><span class="sxs-lookup"><span data-stu-id="e3ef8-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="e3ef8-147">ウイルス対策の定義</span><span class="sxs-lookup"><span data-stu-id="e3ef8-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="e3ef8-148">各スキャンで更新</span><span class="sxs-lookup"><span data-stu-id="e3ef8-148">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="e3ef8-149">実行する Office プロアクティブ プラス] をクリックします</span><span class="sxs-lookup"><span data-stu-id="e3ef8-149">Office Pro-Plus click to run</span></span></td><td colspan="4"><span data-ttu-id="e3ef8-150">半年を 1 チャネルに配置</span><span class="sxs-lookup"><span data-stu-id="e3ef8-150">Aligned with semi-annual channel</span></span></td></tr>
</table>


## <a name="windows-insider-program"></a><span data-ttu-id="e3ef8-151">Windows 内部からのプログラム</span><span class="sxs-lookup"><span data-stu-id="e3ef8-151">Windows Insider Program</span></span>

<span data-ttu-id="e3ef8-p106">Microsoft 管理されたデスクトップは、Windows の内部からのプログラムの一部であるデバイスをサポートしていません。このプログラムでは、プレリリース版の Windows ソフトウェアの検証に使用し、ミッション ・ クリティカルなデバイスを対象としています。重要 Microsoft イニシアチブが、ものではありませんの運用環境での広範な展開。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p106">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. This program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="e3ef8-155">Windows の内部からのビルドで検出されたすべてのデバイスでは、テスト リングに配置され、Sla の更新に含まれません。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-155">Any devices found with Windows Insider builds will be put into the Test ring and not be included for update SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="e3ef8-156">帯域幅管理</span><span class="sxs-lookup"><span data-stu-id="e3ef8-156">Bandwidth management</span></span>

<span data-ttu-id="e3ef8-p107">配信の最適化は、すべてのオペレーティング ・ システムとドライバーの更新に使用されます。企業ネットワーク内のピアからの更新を取得することで、Windows Update (WU) サービスからのダウンロードのサイズを最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="e3ef8-p107">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


