---
title: 別の地域の場所に SharePoint サイトを移動する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: 複数地域の環境内SharePoint別の地域の場所にサイトを移動し、ユーザーに変更の期待を伝える方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a49098045dbce94ef1c474497b8da1b397ac0b0
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362356"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="d7e90-103">別の地域の場所に SharePoint サイトを移動する</span><span class="sxs-lookup"><span data-stu-id="d7e90-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="d7e90-104">SharePoint サイトの地域移動を使って、SharePoint サイトを複数の地域環境内にある別の地域の場所へ移動させることができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="d7e90-105">次のサイトの種類は地域のジオ位置情報間を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="d7e90-106">Microsoft 365グループ接続サイト (グループに関連付けられているサイトを含むMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7e90-106">Microsoft 365 Group-connected sites, including those associated with Microsoft Teams</span></span>
- <span data-ttu-id="d7e90-107">Microsoft 365 グループと関連付けのないモダン サイト</span><span class="sxs-lookup"><span data-stu-id="d7e90-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="d7e90-108">従来の SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="d7e90-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="d7e90-109">コミュニケーション サイト</span><span class="sxs-lookup"><span data-stu-id="d7e90-109">Communication sites</span></span>

<span data-ttu-id="d7e90-110">ジオ位置情報間でサイトを移動するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="d7e90-111">サイトの内容によりますが、約4～6時間のSharePoint サイトの地域移動中は、読み取り専用ウィンドウになります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d7e90-112">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d7e90-112">Best practices</span></span>

- <span data-ttu-id="d7e90-113">その手順に慣れるために、テスト サイトで SharePoint サイトを移動してみてください。</span><span class="sxs-lookup"><span data-stu-id="d7e90-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span>
- <span data-ttu-id="d7e90-114">スケジュールまたは移動を実行する前に、サイトを移動できるかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span>
- <span data-ttu-id="d7e90-115">可能であれば、地域間の移動スケジュールはユーザーへの影響を減らすために営業時間外に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="d7e90-116">サイトの移動前に影響を受けるユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-116">Communicate with impacted users prior to the sites move.</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="d7e90-117">ユーザーへの連絡</span><span class="sxs-lookup"><span data-stu-id="d7e90-117">Communicating to your users</span></span>

<span data-ttu-id="d7e90-118">ジオ位置情報間で SharePoint サイトを移動する場合は、想定される動作をサイトのユーザー (一般的にサイトの編集権限がある全てのユーザー) に通知することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d7e90-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="d7e90-119">これにより、ユーザーの混乱やヘルプデスクへの問い合わせを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="d7e90-120">移動する前に、次の情報をサイトのユーザーへメールで連絡してください。</span><span class="sxs-lookup"><span data-stu-id="d7e90-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="d7e90-121">移動開始予定時刻と予定所要時間</span><span class="sxs-lookup"><span data-stu-id="d7e90-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="d7e90-122">サイトの移動先となるジオ位置情報と、新しい位置情報にアクセスするための URL</span><span class="sxs-lookup"><span data-stu-id="d7e90-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="d7e90-123">移動中はファイルを閉じ、編集を加えないこと。</span><span class="sxs-lookup"><span data-stu-id="d7e90-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="d7e90-124">移動してもファイルのアクセス許可と共有設定は変更されないこと。</span><span class="sxs-lookup"><span data-stu-id="d7e90-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="d7e90-125">複数の地域環境でのユーザー エクスペリエンスから予想されること</span><span class="sxs-lookup"><span data-stu-id="d7e90-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="d7e90-126">移動が正常に終了した時点で、作業を再開できることを伝える電子メールをユーザーに送信してください。</span><span class="sxs-lookup"><span data-stu-id="d7e90-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="d7e90-127">SharePoint サイトのスケジュール設定に移動します</span><span class="sxs-lookup"><span data-stu-id="d7e90-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="d7e90-128">SharePoint サイトの移動を事前にスケジュールすることができます (この記事の後半でご説明します)。</span><span class="sxs-lookup"><span data-stu-id="d7e90-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="d7e90-129">次のように移動をスケジュールします:</span><span class="sxs-lookup"><span data-stu-id="d7e90-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="d7e90-130">一度に最大 4,000 件の移動をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="d7e90-131">移動開始後はスケジュールを追加でき、常時最大 4,000 件の保留中の移動をキューに置いておけます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>

<span data-ttu-id="d7e90-132">SharePoint サイトの地域移動を後でスケジュール設定するには、移動開始時に次のいずれかのパラメーターを含みます:</span><span class="sxs-lookup"><span data-stu-id="d7e90-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>

- <span data-ttu-id="d7e90-133">`PreferredMoveBeginDate` -移動は、この指定時刻に開始されると見込まれます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="d7e90-134">`PreferredMoveEndDate` -移動は、ベストエフォート方式でこの指定時刻に完了すると見込まれます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span>

<span data-ttu-id="d7e90-135">両方のパラメーターの時間を協定世界時 (UTC) で指定してください。</span><span class="sxs-lookup"><span data-stu-id="d7e90-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="d7e90-136">サイトの移動</span><span class="sxs-lookup"><span data-stu-id="d7e90-136">Moving the site</span></span>

<span data-ttu-id="d7e90-137">SharePoint サイトの地域移動は　サイトがあるジオ位置情報でSharePoint の管理 URLから接続し、実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="d7e90-138">たとえば、サイト URL が次の場合は <https://contosohealthcare.sharepoint.com/sites/Turbines> 、次の SharePoint管理者 URL に接続します <https://contosohealthcare-admin.sharepoint.com> 。</span><span class="sxs-lookup"><span data-stu-id="d7e90-138">For example, if the site URL is <https://contosohealthcare.sharepoint.com/sites/Turbines>, connect to the SharePoint Admin URL at <https://contosohealthcare-admin.sharepoint.com>:</span></span>

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint[オンライン管理シェル] ウィンドウに[Connect-SPOService]](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a><span data-ttu-id="d7e90-140">環境の検証</span><span class="sxs-lookup"><span data-stu-id="d7e90-140">Validating the environment</span></span>

<span data-ttu-id="d7e90-141">サイトの移動をスケジュールする前に、サイトが移動できるか検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7e90-141">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="d7e90-142">サイトの移動はサポートしていません:</span><span class="sxs-lookup"><span data-stu-id="d7e90-142">We do not support moving sites with:</span></span>

- <span data-ttu-id="d7e90-143">Business Connectivity Services</span><span class="sxs-lookup"><span data-stu-id="d7e90-143">Business Connectivity Services</span></span>
- <span data-ttu-id="d7e90-144">InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="d7e90-144">InfoPath forms</span></span>
- <span data-ttu-id="d7e90-145">Information Rights Management (IRM) テンプレートの適用</span><span class="sxs-lookup"><span data-stu-id="d7e90-145">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="d7e90-146">すべてのジオ位置情報に互換性があることを確認するために、 `Get-SPOGeoMoveCrossCompatibilityStatus`を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-146">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="d7e90-147">すべてのジオ位置情報と、その環境が移動先のジオ位置情報と互換性があるかどうかを表示します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-147">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="d7e90-148">サイトでの検証のみのチェックを実行するには、`-ValidationOnly` パラメーターで`Start-SPOSiteContentMove`を使い、サイトが移動できるか検証します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-148">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="d7e90-149">例:</span><span class="sxs-lookup"><span data-stu-id="d7e90-149">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="d7e90-150">サイトが移動準備完了の場合、*正常に完了*　と返ってきます。ブロックされている状態がある場合は、*失敗* と返ってきます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-150">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="d7e90-151">Microsoft 365 グループと関連付けられていないサイトへ SharePoint サイトの地域の移動を開始する</span><span class="sxs-lookup"><span data-stu-id="d7e90-151">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="d7e90-152">既定値では、サイトの最初のURL は移動先のジオ位置情報の URL に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-152">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="d7e90-153">例:</span><span class="sxs-lookup"><span data-stu-id="d7e90-153">For example:</span></span>

<span data-ttu-id="d7e90-154"><https://Contoso.sharepoint.com/sites/projectx> から <https://ContosoEUR.sharepoint.com/sites/projectx></span><span class="sxs-lookup"><span data-stu-id="d7e90-154"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projectx></span></span>

<span data-ttu-id="d7e90-155">Microsoft 365 グループと関連付けられていないサイトは、`-DestinationUrl` パラメーターを使ってサイト名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-155">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="d7e90-156">例:</span><span class="sxs-lookup"><span data-stu-id="d7e90-156">For example:</span></span>

<span data-ttu-id="d7e90-157"><https://Contoso.sharepoint.com/sites/projectx> から <https://ContosoEUR.sharepoint.com/sites/projecty></span><span class="sxs-lookup"><span data-stu-id="d7e90-157"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projecty></span></span>

<span data-ttu-id="d7e90-158">サイトの移動を開始するには、次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="d7e90-158">To start the site move, run:</span></span>

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Start-SPOSiteContentMove コマンドレットを示す PowerShell ウィンドウのスクリーン ショット](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="d7e90-160">Microsoft 365 グループが接続されているサイトへ SharePoint サイトの地域の移動を開始する</span><span class="sxs-lookup"><span data-stu-id="d7e90-160">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="d7e90-161">Office 365 グループ接続のサイトへ移動するには、グローバル管理者または SharePoint 管理者がまず、優先されるデータの場所 (PDL) を Office 365 グループの属性に最初に変更しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d7e90-161">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="d7e90-162">Microsoft 365 グループの PDL を設定するには:</span><span class="sxs-lookup"><span data-stu-id="d7e90-162">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

<span data-ttu-id="d7e90-163">PDL を更新したら、サイトの移動を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-163">Once you have updated the PDL, you can start the site move:</span></span>

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="d7e90-164">SharePoint サイトジオへの移動をキャンセルする</span><span class="sxs-lookup"><span data-stu-id="d7e90-164">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="d7e90-165">その移動が実行されていない、または`Stop-SPOSiteContentMove`コマンドレットを使って完了した場合、SharePoint サイトの地域移動を停止できます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-165">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="d7e90-166">SharePoint サイトの地域移動の状況を確認する</span><span class="sxs-lookup"><span data-stu-id="d7e90-166">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="d7e90-167">次のコマンドレットを使用して接続している地域外でのサイトの移動状況を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-167">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="d7e90-168">[Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (グループ接続以外のサイト)</span><span class="sxs-lookup"><span data-stu-id="d7e90-168">[Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="d7e90-169">[Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (グループ接続サイト)</span><span class="sxs-lookup"><span data-stu-id="d7e90-169">[Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (Group-connected sites)</span></span>

<span data-ttu-id="d7e90-170">`-SourceSiteUrl` パラメーターを使用して、移動状況を確認したいサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-170">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="d7e90-171">移動状況については、次に示す表で説明します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-171">The move statuses are described in the following table.</span></span>

****

|<span data-ttu-id="d7e90-172">状態</span><span class="sxs-lookup"><span data-stu-id="d7e90-172">Status</span></span>|<span data-ttu-id="d7e90-173">説明</span><span class="sxs-lookup"><span data-stu-id="d7e90-173">Description</span></span>|
|---|---|
|<span data-ttu-id="d7e90-174">トリガーの準備</span><span class="sxs-lookup"><span data-stu-id="d7e90-174">Ready to Trigger</span></span>|<span data-ttu-id="d7e90-175">移動は開始されていません。</span><span class="sxs-lookup"><span data-stu-id="d7e90-175">The move has not started.</span></span>|
|<span data-ttu-id="d7e90-176">スケジュール済み</span><span class="sxs-lookup"><span data-stu-id="d7e90-176">Scheduled</span></span>|<span data-ttu-id="d7e90-177">移動がキューにあり、まだ開始されていません。</span><span class="sxs-lookup"><span data-stu-id="d7e90-177">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="d7e90-178">InProgress (n/4)</span><span class="sxs-lookup"><span data-stu-id="d7e90-178">InProgress (n/4)</span></span>|<span data-ttu-id="d7e90-179">移動は、検証 (1/4)、バックアップ (2/4)、復元 (3/4)、クリーンアップ (4/4) のいずれかの状態で進行中です。</span><span class="sxs-lookup"><span data-stu-id="d7e90-179">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="d7e90-180">Success</span><span class="sxs-lookup"><span data-stu-id="d7e90-180">Success</span></span>|<span data-ttu-id="d7e90-181">移動は正常に完了しています。</span><span class="sxs-lookup"><span data-stu-id="d7e90-181">The move has completed successfully.</span></span>|
|<span data-ttu-id="d7e90-182">Failed</span><span class="sxs-lookup"><span data-stu-id="d7e90-182">Failed</span></span>|<span data-ttu-id="d7e90-183">移動は失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d7e90-183">The move failed.</span></span>|
|

<span data-ttu-id="d7e90-184">移動に関する追加情報を確認する `-Verbose` オプションを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-184">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="d7e90-185">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d7e90-185">User experience</span></span>

<span data-ttu-id="d7e90-186">サイトが別のジオ位置情報へ移動した場合は、サイトユーザーに最小限の中断があることを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-186">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="d7e90-187">移動中は簡単な読み取り専用状態になることに加えて、既存のリンクとアクセス許可は移動の完了後に引き続き想定通りに操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-187">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="d7e90-188">サイト</span><span class="sxs-lookup"><span data-stu-id="d7e90-188">Site</span></span>

<span data-ttu-id="d7e90-189">移動の実行中は、サイトは読み取り専用に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-189">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="d7e90-190">移動の完了後に、ブックマークまたは他のリンクをクリックすると、新しいジオ位置情報の新しいサイトがユーザーに指定されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-190">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="d7e90-191">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d7e90-191">Permissions</span></span>

<span data-ttu-id="d7e90-192">サイトへのアクセス許可を持つユーザーは、移動中および移動完了後のサイトに引き続きアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-192">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-app"></a><span data-ttu-id="d7e90-193">同期アプリ</span><span class="sxs-lookup"><span data-stu-id="d7e90-193">Sync app</span></span>

<span data-ttu-id="d7e90-194">サイトの移動が完了すると、同期アプリは自動的に検出され、新しいサイトの場所への同期をシームレスに転送します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-194">The sync app will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="d7e90-195">ユーザーはもう一度サインインまたはその他のアクションをする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d7e90-195">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="d7e90-196">(必要な同期アプリのバージョン 17.3.6943.0625 以降)。</span><span class="sxs-lookup"><span data-stu-id="d7e90-196">(Version 17.3.6943.0625 or later of the sync app required.)</span></span>

<span data-ttu-id="d7e90-197">移動の進行中にユーザーがファイルを更新すると、移動中にファイルのアップロードが保留中であるという通知が同期アプリによって通知されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-197">If a user updates a file while the move is in progress, the sync app will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="d7e90-198">共有リンク</span><span class="sxs-lookup"><span data-stu-id="d7e90-198">Sharing links</span></span>

<span data-ttu-id="d7e90-199">SharePoint サイトの地域移動の完了時に、移動されたファイルの既存の共有リンクは、新しいジオ位置情報に自動的にリダイレクトされるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-199">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="d7e90-200">最近使用された Office のファイル (MRU)</span><span class="sxs-lookup"><span data-stu-id="d7e90-200">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="d7e90-201">MRU サービスは、移動が完了するとサイトとコンテンツの URL が更新されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-201">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="d7e90-202">Word、Excel、PowerPoint に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-202">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="d7e90-203">OneNote エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d7e90-203">OneNote experience</span></span>

<span data-ttu-id="d7e90-204">OneNote win32 クライアントと UWP (ユニバーサル) アプリは、サイトの移動完了後に新しいサイトの場所を自動的に検出し、シームレスにノートブックを同期します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-204">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="d7e90-205">ユーザーはもう一度サインインまたはその他のアクションをする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d7e90-205">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="d7e90-206">サイトの移動が進行中にノートブックの同期が失敗する時だけ、ユーザーにインジケーターで表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-206">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="d7e90-207">このエクスペリエンスは、次の OneNote クライアント バージョンで使用できます:</span><span class="sxs-lookup"><span data-stu-id="d7e90-207">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="d7e90-208">OneNote win32: バージョン 16.0.8326.2096 (以降)</span><span class="sxs-lookup"><span data-stu-id="d7e90-208">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="d7e90-209">OneNote UWP: バージョン 16.0.8431.1006 (以降)</span><span class="sxs-lookup"><span data-stu-id="d7e90-209">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="d7e90-210">OneNote モバイル アプリ: バージョン 16.0.8431.1011 (以降)</span><span class="sxs-lookup"><span data-stu-id="d7e90-210">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="d7e90-211">Teams (Microsoft 365 グループと接続されているサイトに適用)</span><span class="sxs-lookup"><span data-stu-id="d7e90-211">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="d7e90-212">SharePoint サイトの地域の移動が完了すると、ユーザーは Teams アプリの Microsoft 365 グループ サイトのファイルにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-212">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="d7e90-213">さらに、地域移動前にサイトからチーム チャット経由で共有したファイルは、移動が完了後に引き続き操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-213">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="d7e90-214">iOS/Android 用 SharePoint モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="d7e90-214">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="d7e90-215">SharePoint モバイル アプリは、地域間で互換性があり、サイトの新しいジオ位置情報を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="d7e90-215">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="d7e90-216">SharePoint ワークフロー</span><span class="sxs-lookup"><span data-stu-id="d7e90-216">SharePoint workflows</span></span>

<span data-ttu-id="d7e90-217">SharePoint 2013 ワークフローは、サイトの移動後に再発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-217">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="d7e90-218">SharePoint 2010 ワークフローは、正常に動作し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-218">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="d7e90-219">アプリ</span><span class="sxs-lookup"><span data-stu-id="d7e90-219">Apps</span></span>

<span data-ttu-id="d7e90-220">アプリを使用してサイトを移動すると、移動先のジオ位置情報に接続できない場合があるので、サイトの新しいジオ位置情報でアプリを再インスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-220">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="d7e90-221">フロー</span><span class="sxs-lookup"><span data-stu-id="d7e90-221">Flow</span></span>

<span data-ttu-id="d7e90-222">ほとんどの場合、フローは SharePoint サイトの地域移動後に引き続き操作することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-222">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="d7e90-223">移動が完了したらテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7e90-223">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="d7e90-224">PowerApps</span><span class="sxs-lookup"><span data-stu-id="d7e90-224">PowerApps</span></span>

<span data-ttu-id="d7e90-225">PowerAppsは、移動先の位置情報で再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e90-225">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="d7e90-226">ジオ位置情報間のデータ移動</span><span class="sxs-lookup"><span data-stu-id="d7e90-226">Data movement between geo locations</span></span>

<span data-ttu-id="d7e90-227">SharePoint にサイトとそのファイルに関連付けられているメタデータが保存されている場合は、コンテンツの Azure Blob ストレージを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-227">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="d7e90-228">その元のジオ位置情報から移動先のジオ位置情報へ移動後、サービスも関連付けられている Blob ストレージへ移動します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-228">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="d7e90-229">BLOB ストレージは約40日で移動を完了します。</span><span class="sxs-lookup"><span data-stu-id="d7e90-229">Blob Storage moves complete in approximately 40 days.</span></span>