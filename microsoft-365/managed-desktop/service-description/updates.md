---
title: Microsoft マネージド デスクトップでの更新プログラムの処理方法
description: 管理されたデスクトップのマイクロソフトの最新の状態を保持することは、速度と安定性のバランスです。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869105"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="106d7-104">Microsoft マネージド デスクトップでの更新プログラムの処理方法</span><span class="sxs-lookup"><span data-stu-id="106d7-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="106d7-p101">Microsoft 管理されたデスクトップは、最新のクラウド ・ ベースのインフラストラクチャをすべてのデバイスを接続します。速度と安定性のバランスは、Windows、Office、ドライバー、ファームウェア、および Microsoft ストア ビジネス アプリケーションの更新プログラムを最新に保ちます。OS を確認するのには展開リングが使用され、ポリシーを安全に公開します。</span><span class="sxs-lookup"><span data-stu-id="106d7-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-groups"></a><span data-ttu-id="106d7-108">グループを更新します。</span><span class="sxs-lookup"><span data-stu-id="106d7-108">Update groups</span></span>

<span data-ttu-id="106d7-109">Microsoft 管理されたデスクトップでは、更新プログラムを管理するのには Azure AD の 4 つのグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="106d7-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="106d7-p102">テスト: 非本番デバイスがテナントの残りの部分の間で変更内容を展開する前に変更内容を検証するためのものです。このリング内のデバイスでは、文書化されたエンド ユーザー サポートの対象外です。</span><span class="sxs-lookup"><span data-stu-id="106d7-p102">Test: Non-production devices intended to validate changes prior to deploying the changes across the rest of the tenant. Devices in this ring are out of scope for documented end user support.</span></span> 
- <span data-ttu-id="106d7-112">: 最初には早期ソフトウェアが含まれていますデバイスは、プレリリース版更新プログラムをされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="106d7-112">First: Contains early software adopters, and devices may be subject to pre-release updates.</span></span>
- <span data-ttu-id="106d7-p103">速度の安定性を優先順位を付けて高速: です。広範なグループに提供する前に、品質の問題を検出するために便利です。</span><span class="sxs-lookup"><span data-stu-id="106d7-p103">Fast: Prioritizes speed over stability. Useful for detecting quality issues before they are offered to the Broad group.</span></span> 
- <span data-ttu-id="106d7-p104">広範な: 最後にグループに利用可能な機能と品質の更新。このグループは、テナント内のユーザーの大部分が含まれていますされ、したがって展開の速度での安定性を優先します。</span><span class="sxs-lookup"><span data-stu-id="106d7-p104">Broad: Last group to have feature and quality updates available. This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span>

<span data-ttu-id="106d7-p105">Microsoft によってリリースされる更新プログラムは累積であり、品質や機能の更新プログラムとして分類することがあります。詳細についてを参照してください[Windows の更新プログラム: よく寄せられる質問](https://support.microsoft.com/help/12373/windows-update-faq)。</span><span class="sxs-lookup"><span data-stu-id="106d7-p105">Updates released by Microsoft are cumulative and may be categorized as quality or feature updates. For more information, see [Windows Update: FAQ](https://support.microsoft.com/help/12373/windows-update-faq).</span></span> 

<span data-ttu-id="106d7-119">展開機能をアップデートする方法。</span><span class="sxs-lookup"><span data-stu-id="106d7-119">How update deployment works:</span></span>
- <span data-ttu-id="106d7-120">Microsoft 管理されたデスクトップでは、以下に指定したスケジュールの設定に基づいて新しい機能や品質の更新を展開します。</span><span class="sxs-lookup"><span data-stu-id="106d7-120">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="106d7-p106">展開中に障害やシステム停止 (遠隔測定の信号とエンド ・ ユーザー ・ サポート ・ システムに基づく) の Microsoft 管理されたデスクトップを監視します。いずれかが検出された場合は、現在および将来のすべてのグループへの展開がすぐに一時停止しました。</span><span class="sxs-lookup"><span data-stu-id="106d7-p106">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on telemetry signals and end-user support system). If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="106d7-123">例: 最初のグループに、品質の更新プログラムの展開中に問題が見つかった場合、最初、高速、および広範な更新プログラムの展開すべてが一時停止される問題が解決されるまでです。</span><span class="sxs-lookup"><span data-stu-id="106d7-123">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="106d7-124">Microsoft デスクトップ IT 管理者の管理ポータルにチケットを送信することにより互換性の問題を報告することがあります。</span><span class="sxs-lookup"><span data-stu-id="106d7-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="106d7-p107">機能と品質の更新プログラムが個別に一時停止します。一時停止は、既定では、35 日で有効にですが、削減または問題を改善するかどうかによって拡張します。</span><span class="sxs-lookup"><span data-stu-id="106d7-p107">Feature and quality updates are paused independently. Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="106d7-127">グループは、使用されていないが、以下のスケジュールに従って配置を再開します。</span><span class="sxs-lookup"><span data-stu-id="106d7-127">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="106d7-128">この展開プロセス タイムラインがそれぞれ異なりますが、機能と品質の両方の更新プログラムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="106d7-128">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="106d7-129">配置の設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="106d7-129">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="106d7-130">更新の種類</span><span class="sxs-lookup"><span data-stu-id="106d7-130">Update type</span></span></th><th><span data-ttu-id="106d7-131">テスト</span><span class="sxs-lookup"><span data-stu-id="106d7-131">Test</span></span></th><th><span data-ttu-id="106d7-132">まずは</span><span class="sxs-lookup"><span data-stu-id="106d7-132">First</span></span></th><th><span data-ttu-id="106d7-133">高速します。</span><span class="sxs-lookup"><span data-stu-id="106d7-133">Fast</span></span></th><th><span data-ttu-id="106d7-134">広範です</span><span class="sxs-lookup"><span data-stu-id="106d7-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="106d7-135">オペレーティング ・ システムの品質の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="106d7-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="106d7-136">0 日</span><span class="sxs-lookup"><span data-stu-id="106d7-136">0 days</span></span></td><td><span data-ttu-id="106d7-137">0 日</span><span class="sxs-lookup"><span data-stu-id="106d7-137">0 days</span></span></td><td><span data-ttu-id="106d7-138">0 日</span><span class="sxs-lookup"><span data-stu-id="106d7-138">0 days</span></span></td><td><span data-ttu-id="106d7-139">3 日間</span><span class="sxs-lookup"><span data-stu-id="106d7-139">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="106d7-140">オペレーティング システムの機能の更新</span><span class="sxs-lookup"><span data-stu-id="106d7-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="106d7-141">0 日</span><span class="sxs-lookup"><span data-stu-id="106d7-141">0 days</span></span></td><td><span data-ttu-id="106d7-142">30 日間</span><span class="sxs-lookup"><span data-stu-id="106d7-142">30 days</span></span></td><td><span data-ttu-id="106d7-143">60 日</span><span class="sxs-lookup"><span data-stu-id="106d7-143">60 days</span></span></td><td><span data-ttu-id="106d7-144">90 日間</span><span class="sxs-lookup"><span data-stu-id="106d7-144">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="106d7-145">ドライバーやファームウェア</span><span class="sxs-lookup"><span data-stu-id="106d7-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="106d7-146">品質の更新プログラムのスケジュールをに従って、</span><span class="sxs-lookup"><span data-stu-id="106d7-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="106d7-147">ウイルス対策の定義</span><span class="sxs-lookup"><span data-stu-id="106d7-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="106d7-148">各スキャンで更新</span><span class="sxs-lookup"><span data-stu-id="106d7-148">Updated with each scan</span></span></td></tr>
</table>

<span data-ttu-id="106d7-p108">この遅延期間は、高度なセキュリティとすべてのユーザーのパフォーマンス標準を確実に意図的に設計されています。さらに、Microsoft 管理されたデスクトップのすべてのデバイスとさまざまなスコープや更新プログラムの影響の間で収集したデータに基づいて、Microsoft の管理されたデスクトップを予約広告の配置のすべてのグループの上の遅延期間の長さを変更するのには柔軟性特別な基準です。</span><span class="sxs-lookup"><span data-stu-id="106d7-p108">These deferral periods are intentionally designed to ensure high security and performance standards for all users. Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>

## <a name="windows-insider-program"></a><span data-ttu-id="106d7-151">Windows 内部からのプログラム</span><span class="sxs-lookup"><span data-stu-id="106d7-151">Windows Insider Program</span></span>

<span data-ttu-id="106d7-p109">Microsoft 管理されたデスクトップは、Windows の内部からのプログラムの一部であるデバイスをサポートしていません。Windows の内部プログラム プレリリース版の Windows ソフトウェアの検証に使用であり、ミッション ・ クリティカルなデバイス。重要 Microsoft イニシアチブが、ものではありませんの運用環境での広範な展開。</span><span class="sxs-lookup"><span data-stu-id="106d7-p109">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. The Windows Insider program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="106d7-155">Windows の内部からのビルドで検出されたすべてのデバイスがテスト グループに配置され、ないを対象に含める更新プログラムのサービス レベル契約 (Sla。</span><span class="sxs-lookup"><span data-stu-id="106d7-155">Any devices found with Windows Insider builds will be put into the Test group and not be included for update service level agreements (SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="106d7-156">帯域幅管理</span><span class="sxs-lookup"><span data-stu-id="106d7-156">Bandwidth management</span></span>

<span data-ttu-id="106d7-p110">配信の最適化は、すべてのオペレーティング ・ システムとドライバーの更新に使用されます。企業ネットワーク内のピアからの更新を取得することで、Windows Update (WU) サービスからのダウンロードのサイズを最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="106d7-p110">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


