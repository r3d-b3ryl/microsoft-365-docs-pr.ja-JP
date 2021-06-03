---
title: ポータル起動スケジューラを使用してポータルを起動する
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: この記事では、ポータル起動スケジューラを使用してポータルを起動する方法について説明します。
ms.openlocfilehash: ac55a5b0cc9d252642c890b78ccec1ba720f0957
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730260"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="4babc-103">ポータル起動スケジューラを使用してSharePointを起動する</span><span class="sxs-lookup"><span data-stu-id="4babc-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="4babc-104">ポータルは、トラフィックが多いイントラネット上の SharePoint コミュニケーション サイトです。数週間の間に 10,000 人から 100,000 人を超える視聴者が存在するサイトです。</span><span class="sxs-lookup"><span data-stu-id="4babc-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="4babc-105">ポータル起動スケジューラを使用してポータルを起動し、新しいポータルにアクセスするときにユーザーがスムーズに表示SharePointします。</span><span class="sxs-lookup"><span data-stu-id="4babc-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="4babc-106">ポータル起動スケジューラは、ウェーブでビューアーをバッチ処理し、新しいポータルの URL リダイレクトを管理することで、段階的なロールアウトアプローチに従うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4babc-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="4babc-107">各ウェーブの起動中に、ユーザーフィードバックを収集し、ポータルのパフォーマンスを監視し、起動を一時停止して問題を解決してから、次のウェーブに進みます。</span><span class="sxs-lookup"><span data-stu-id="4babc-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="4babc-108">ポータルの起動を計画[する方法の詳細については、SharePoint。](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="4babc-108">Learn more about how to [plan a portal launch in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="4babc-109">**リダイレクトには、次の 2 種類があります。**</span><span class="sxs-lookup"><span data-stu-id="4babc-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="4babc-110">**双方向**: 新しいモダン SharePointポータルを起動して、既存のSharePointまたはモダン ポータルを置き換える</span><span class="sxs-lookup"><span data-stu-id="4babc-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="4babc-111">**一時ページへのリダイレクト**: 既存のポータルを使用SharePoint新しいモダン SharePointポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="4babc-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="4babc-112">サイトのアクセス許可は、起動の一環としてウェーブとは別に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="4babc-113">たとえば、組織全体のポータルをリリースする場合は、アクセス許可を "外部ユーザーを除くすべてのユーザー" に設定し、セキュリティ グループを使用してユーザーをウェーブに分けられます。</span><span class="sxs-lookup"><span data-stu-id="4babc-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="4babc-114">ウェーブにセキュリティ グループを追加しても、そのセキュリティ グループはサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4babc-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="4babc-115">この機能は、2021 年 5 月からターゲット リリースのお客様向け SharePoint コミュニケーション サイトのホーム ページにある 設定 パネルからアクセス可能になり、2021 年 7 月までにはすべてのお客様が利用できる予定です。 </span><span class="sxs-lookup"><span data-stu-id="4babc-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="4babc-116">このツールの PowerShell バージョンは現在利用できます</span><span class="sxs-lookup"><span data-stu-id="4babc-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="4babc-117">この機能は、最新の通信サイトでのみSharePointできます。</span><span class="sxs-lookup"><span data-stu-id="4babc-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="4babc-118">ポータルの起動をカスタマイズおよびスケジュールするには、サイトのサイト所有者のアクセス許可が必要です</span><span class="sxs-lookup"><span data-stu-id="4babc-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="4babc-119">起動は少なくとも 7 日前にスケジュールする必要があります。各ウェーブは 1 日から 7 日間続く場合があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="4babc-120">必要なウェーブの数は、予想されるユーザー数によって自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="4babc-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="4babc-121">ポータルの起動をスケジュールする前[](https://aka.ms/perftool)SharePointページ診断ツールを実行して、サイトのホーム ページが正常な状態にあるか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="4babc-122">起動の最後に、サイトへのアクセス許可を持つすべてのユーザーが新しいサイトにアクセスできます</span><span class="sxs-lookup"><span data-stu-id="4babc-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="4babc-123">組織で Viva [Connections](https://docs.microsoft.com/SharePoint/viva-connections)を使用している場合、ユーザーは Microsoft Teams アプリ バーに組織のアイコンを表示する場合があります。ただし、アイコンが選択されている場合、ユーザーはウェーブが起動するまでポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4babc-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="4babc-124">この機能は、ドイツ、Office 365 21Vianet (中国Office 365)、米国政府の計画ではMicrosoft 365使用できません。</span><span class="sxs-lookup"><span data-stu-id="4babc-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="4babc-125">ポータル起動スケジューラ オプションの違いを理解します。</span><span class="sxs-lookup"><span data-stu-id="4babc-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="4babc-126">以前は、ポータルの起動は PowerShell 経由でのみSharePointでした。</span><span class="sxs-lookup"><span data-stu-id="4babc-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="4babc-127">これで、ポータルの起動のスケジュールと管理に役立つ 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4babc-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="4babc-128">両方のツールの主な違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4babc-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="4babc-129">**SharePointPowerShell のバージョン:**</span><span class="sxs-lookup"><span data-stu-id="4babc-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="4babc-130">PowerShell で管理者資格情報を使用[するにはSharePoint必要](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="4babc-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="4babc-131">1 つのウェーブの最小要件</span><span class="sxs-lookup"><span data-stu-id="4babc-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="4babc-132">協定世界時 (UTC) タイム ゾーンに基づいて起動をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="4babc-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="4babc-133">**製品内バージョン:**</span><span class="sxs-lookup"><span data-stu-id="4babc-133">**In-product version:**</span></span>

- <span data-ttu-id="4babc-134">サイト所有者の資格情報が必要です</span><span class="sxs-lookup"><span data-stu-id="4babc-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="4babc-135">2 つのウェーブの最小要件</span><span class="sxs-lookup"><span data-stu-id="4babc-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="4babc-136">地域の設定に示されているポータルのローカル タイム ゾーンに基づいて起動をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="4babc-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="4babc-137">ポータル起動スケジューラの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="4babc-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="4babc-138">ポータル起動スケジューラ ツールを使用する[](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)前に、サイトの所有者、サイト メンバー、または訪問者としてサイトのアクセス許可を使用して、このサイトにアクセスする必要があるすべてのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4babc-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="4babc-139">次に、ポータル起動スケジューラにアクセスして、次のいずれかの方法でポータルの起動のスケジュールを開始します。</span><span class="sxs-lookup"><span data-stu-id="4babc-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="4babc-140">**オプション 1:** ホーム ページへの変更を編集して再発行する最初の数回 (またはホーム ページ バージョン 3.0 まで) は、ポータル起動スケジューラ ツールの使用を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4babc-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="4babc-141">[起動 **のスケジュール] を** 選択して、スケジュールを進め続けろ。</span><span class="sxs-lookup"><span data-stu-id="4babc-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="4babc-142">または、[ **再公開] を選択** して、起動をスケジュールせずにページの編集内容を再発行します。</span><span class="sxs-lookup"><span data-stu-id="4babc-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![ホーム ページの再発行時にポータル起動スケジューラを使用するプロンプトのイメージ](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="4babc-144">**オプション 2:** いつでも、SharePoint コミュニケーション サイトのホーム ページに移動し **、[設定]** を選択し、[サイトの起動をスケジュールしてポータルの起動をスケジュールする] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4babc-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![[サイトの起動を設定する] ウィンドウのイメージが強調表示されている](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="4babc-146">次に、ポータルが正常なスコアを受け取るまで [、SharePoint](https://aka.ms/perftool)ツールのページ診断ツールを使用して、ポータルの正常性スコアを確認し、必要に応じてポータルを **改善** します。</span><span class="sxs-lookup"><span data-stu-id="4babc-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="4babc-147">さらに **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4babc-147">Then, select **Next**.</span></span>

    ![ポータル起動スケジューラ ツールのイメージ](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="4babc-149">サイト名と説明をポータル起動スケジューラから編集することはできません。代わりに、ホーム ページから [設定] を選択し、[サイト情報] を選択して変更できます。</span><span class="sxs-lookup"><span data-stu-id="4babc-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="4babc-150">ドロップダウンから **[予想されるユーザー数** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4babc-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="4babc-151">この図は、サイトへのアクセスが必要な可能性が高いユーザーの数を表しています。</span><span class="sxs-lookup"><span data-stu-id="4babc-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="4babc-152">ポータル起動スケジューラは、次のような予想されるユーザーに応じて、最適なウェーブ数を自動的に決定します。</span><span class="sxs-lookup"><span data-stu-id="4babc-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="4babc-153">10k 未満のユーザー: 2 つのウェーブ</span><span class="sxs-lookup"><span data-stu-id="4babc-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="4babc-154">10k ~ 30k のユーザー: 3 つの波</span><span class="sxs-lookup"><span data-stu-id="4babc-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="4babc-155">30k 以上から 100k のユーザー: 5 つのウェーブ</span><span class="sxs-lookup"><span data-stu-id="4babc-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="4babc-156">100,000 人を超えるユーザー: 5 つのウェーブと、100k を超えるユーザーを含むポータルの起動に記載されている手順に従って Microsoft に連絡します。</span><span class="sxs-lookup"><span data-stu-id="4babc-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span> 

5.  <span data-ttu-id="4babc-157">次に、必要な **リダイレクトの種類を** 決定します。</span><span class="sxs-lookup"><span data-stu-id="4babc-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="4babc-158">**オプション 1:** ユーザーを既存の SharePoint ページに送信する (双方向) – 新しいモダン SharePoint ポータルを起動して既存の SharePoint ポータルを置き換える場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4babc-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="4babc-159">アクティブなウェーブのユーザーは、古いサイトと新しいサイトに移動するかどうかに関係なく、新しいサイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="4babc-160">新しいサイトにアクセスしようとする起動されていないウェーブのユーザーは、ウェーブが起動されるまで古いサイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="4babc-161">双方向オプションを使用する場合、起動をスケジュールするユーザーには、他のユーザーポータルに対するサイト所有者のアクセス許可SharePointがあります。</span><span class="sxs-lookup"><span data-stu-id="4babc-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="4babc-162">**オプション 2: 自動** 生成された一時ページにユーザーを送信する (一時的なページ リダイレクト) – 既存のページ が存在しない場合は、一時的なページ リダイレクトSharePoint使用します。</span><span class="sxs-lookup"><span data-stu-id="4babc-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="4babc-163">ユーザーは新しいモダン SharePoint ポータルに移動され、ユーザーが起動されていないウェーブの場合は、一時的なページにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="4babc-164">**オプション 3: ユーザーを外部ページ** に送信する – ユーザーのウェーブが開始されるまで、一時的なランディング ページ エクスペリエンスに外部 URL を提供します。</span><span class="sxs-lookup"><span data-stu-id="4babc-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="4babc-165">対象ユーザーをウェーブに分割します。</span><span class="sxs-lookup"><span data-stu-id="4babc-165">Break up your audience into waves.</span></span> <span data-ttu-id="4babc-166">ウェーブごとに最大 20 のセキュリティ グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="4babc-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="4babc-167">ウェーブの詳細は、各ウェーブが起動するまで編集できます。</span><span class="sxs-lookup"><span data-stu-id="4babc-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="4babc-168">各ウェーブは、少なくとも 1 日 (24 時間) および最大 7 日間続きます。</span><span class="sxs-lookup"><span data-stu-id="4babc-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="4babc-169">これにより、SharePoint技術環境を利用して、大量のサイト ユーザーに順化して拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4babc-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="4babc-170">UI を使用して起動をスケジュールする場合、タイム ゾーンはサイトの地域設定に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="4babc-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="4babc-171">ポータル起動スケジューラは、最小 2 ウェーブに自動的に既定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="4babc-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="4babc-172">ただし、このツールの PowerShell バージョンでは、1 ウェーブが許可されます。</span><span class="sxs-lookup"><span data-stu-id="4babc-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="4babc-173">Microsoft 365は、このバージョンのポータル起動スケジューラではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4babc-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="4babc-174">サイトをすぐ表示する必要があるユーザーを特定し、[ウェーブから除外するユーザー] フィールドに情報 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="4babc-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="4babc-175">これらのユーザーはウェーブから除外され、起動前、起動中、または起動後にはリダイレクトされません。</span><span class="sxs-lookup"><span data-stu-id="4babc-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

8.  <span data-ttu-id="4babc-176">ポータルの起動の詳細を確認し、[スケジュール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4babc-176">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="4babc-177">起動がスケジュールされると、ポータルの起動が再開される前に、SharePoint ポータルのホーム ページに対する変更は正常な診断結果を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-177">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-portal-with-over-100k-users"></a><span data-ttu-id="4babc-178">100k を超えるユーザーがポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="4babc-178">Launch portal with over 100k users</span></span>

<span data-ttu-id="4babc-179">100,000 人を超えるユーザーを含むポータルを起動する予定の場合は、以下の手順に従ってサポート要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="4babc-179">If you are planning to launch a portal with over 100,000 users, please submit a support request following the steps listed below.</span></span> <span data-ttu-id="4babc-180">必要な情報がすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4babc-180">Make sure to include all requested information.</span></span>

<span data-ttu-id="4babc-181">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4babc-181">Follow these steps:</span></span>
1. <span data-ttu-id="4babc-182"> https://admin.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="4babc-182">Navigate to https://admin.microsoft.com</span></span>
2. <span data-ttu-id="4babc-183">新しい管理センター プレビューを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4babc-183">Ensure you are using the new admin center preview.</span></span>
3. <span data-ttu-id="4babc-184">左側のナビゲーション ウィンドウで、[**サポート**]、[**新規お問い合わせ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4babc-184">On the left nav pane, select **Support**, and then select **New Service Request**.</span></span> 


   <span data-ttu-id="4babc-185">これにより、画面の右側にある [**ヘルプが必要ですか?**] ウィンドウがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="4babc-185">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4.  <span data-ttu-id="4babc-186">[問題 **の簡単な説明] 領域で**、「100k ユーザー SharePointポータルを起動する」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4babc-186">In the **Briefly describe your issue** area, enter "Launch SharePoint Portal with 100k users".</span></span></br>
5. <span data-ttu-id="4babc-187">[**サポートに問い合わせる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4babc-187">Select **Contact Support**.</span></span>
6. <span data-ttu-id="4babc-188">[**説明]** で、「100k ユーザー SharePointポータルを起動する」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4babc-188">Under **Description**, enter "Launch SharePoint Portal with 100k users".</span></span> 
7. <span data-ttu-id="4babc-189">残りの情報を入力して、[**連絡してください**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4babc-189">Fill out the remaining info, and select **Contact me**.</span></span>
8. <span data-ttu-id="4babc-190">チケットを作成したら、次の情報をサポート エージェントに提供してください。</span><span class="sxs-lookup"><span data-stu-id="4babc-190">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
- <span data-ttu-id="4babc-191">ポータル URL の起動</span><span class="sxs-lookup"><span data-stu-id="4babc-191">Launch Portal URL's</span></span> 
- <span data-ttu-id="4babc-192">予想されるユーザー数</span><span class="sxs-lookup"><span data-stu-id="4babc-192">Number of users expected</span></span>
- <span data-ttu-id="4babc-193">起動の推定時間</span><span class="sxs-lookup"><span data-stu-id="4babc-193">Estimated time of launch</span></span> 

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="4babc-194">スケジュールされたポータルの起動に変更を加える</span><span class="sxs-lookup"><span data-stu-id="4babc-194">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="4babc-195">起動の詳細は、ウェーブの起動日までウェーブごとに編集できます。</span><span class="sxs-lookup"><span data-stu-id="4babc-195">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="4babc-196">ポータルの起動の詳細を編集するには、[サイトの **起動を** 設定] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4babc-196">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="4babc-197">次に、[編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4babc-197">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="4babc-198">編集が完了したら、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4babc-198">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="4babc-199">スケジュールされたポータルの起動を削除する</span><span class="sxs-lookup"><span data-stu-id="4babc-199">Delete a scheduled portal launch</span></span>

<span data-ttu-id="4babc-200">ポータル起動スケジューラ ツールを使用してスケジュールされた起動は、一部のウェーブが既に起動されている場合でも、いつでもキャンセルまたは削除できます。</span><span class="sxs-lookup"><span data-stu-id="4babc-200">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="4babc-201">ポータルの起動をキャンセルするには、[サイトの起動 **を設定]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="4babc-201">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="4babc-202">次に、[ **削除] を選択** し、下にメッセージが表示された場合は、[削除] を再度 **選択** します。</span><span class="sxs-lookup"><span data-stu-id="4babc-202">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![ポータル起動スケジューラ ツールのイメージ](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="4babc-204">PowerShell Portal 起動スケジューラを使用する</span><span class="sxs-lookup"><span data-stu-id="4babc-204">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="4babc-205">ポータルSharePoint起動スケジューラ ツールは、当初[は SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)経由でのみ利用可能であり、この方法を好むお客様には引き続き PowerShell を通じてサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-205">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="4babc-206">この記事の冒頭の同じメモは、ポータル起動スケジューラの両方のバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4babc-206">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="4babc-207">PowerShell で使用するには、管理者SharePoint必要です。</span><span class="sxs-lookup"><span data-stu-id="4babc-207">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="4babc-208">PowerShell で作成された起動のポータル起動の詳細が表示され、新しいポータル起動スケジューラ ツールで管理SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4babc-208">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="4babc-209">アプリのセットアップとオンラインへのSharePointする</span><span class="sxs-lookup"><span data-stu-id="4babc-209">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="4babc-210">[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="4babc-210">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4babc-p117">SharePoint Online 管理シェルの以前のバージョンがインストールされている場合は、[プログラムの追加と削除] に移動して、"SharePoint Online 管理シェル" をアンインストールします。 </span><span class="sxs-lookup"><span data-stu-id="4babc-p117">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="4babc-212">ダウンロード センター ページで言語を選択して、[ダウンロード] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4babc-212">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="4babc-213">x64 .msi ファイルまたは x86 .msi ファイルのどちらをダウンロードするかを選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="4babc-213">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="4babc-214">Windows の 64 ビット版を実行している場合は x64 ファイルを、32 ビット版を実行している場合は x86 ファイルをそれぞれダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4babc-214">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="4babc-215">不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4babc-215">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="4babc-216">ファイルをダウンロードしたら、それを実行して、セットアップ ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4babc-216">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="4babc-217">Microsoft 365 の[グローバル管理者または SharePoint 管理者](/sharepoint/sharepoint-admin-role)として SharePoint Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="4babc-217">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="4babc-218">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4babc-218">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="4babc-219">既存のポータル起動セットアップを表示する</span><span class="sxs-lookup"><span data-stu-id="4babc-219">View any existing portal launch setups</span></span>

<span data-ttu-id="4babc-220">既存のポータル起動構成がある場合は、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4babc-220">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="4babc-221">サイトでのポータルの起動をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="4babc-221">Schedule a portal launch on the site</span></span>

<span data-ttu-id="4babc-222">必要なウェーブの数は、予想される起動サイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4babc-222">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="4babc-223">10k 未満のユーザー: 1 ウェーブ</span><span class="sxs-lookup"><span data-stu-id="4babc-223">Less than 10k users: One wave</span></span>
- <span data-ttu-id="4babc-224">10k ~ 30k のユーザー: 3 つの波</span><span class="sxs-lookup"><span data-stu-id="4babc-224">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="4babc-225">30k 以上から 100k のユーザー: 5 つのウェーブ</span><span class="sxs-lookup"><span data-stu-id="4babc-225">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="4babc-226">100,000 人を超えるユーザー: 5 つのウェーブと Microsoft アカウント チームに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="4babc-226">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="4babc-227">双方向リダイレクトの手順</span><span class="sxs-lookup"><span data-stu-id="4babc-227">Steps for bidirectional redirection</span></span>

<span data-ttu-id="4babc-228">双方向リダイレクトでは、新しいモダン SharePointオンライン ポータルを起動し、既存の SharePointまたはモダン ポータルを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-228">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="4babc-229">アクティブなウェーブのユーザーは、古いサイトと新しいサイトに移動するかどうかに関係なく、新しいサイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-229">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="4babc-230">新しいサイトにアクセスしようとする起動されていないウェーブのユーザーは、ウェーブが起動されるまで古いサイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-230">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="4babc-231">古いサイトの既定のホーム ページと新しいサイトの既定のホーム ページとの間のリダイレクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4babc-231">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="4babc-232">リダイレクトせずに古いサイトと新しいサイトにアクセスする必要がある管理者または所有者が必要な場合は、パラメーターを使用して一覧に表示 `WaveOverrideUsers` してください。</span><span class="sxs-lookup"><span data-stu-id="4babc-232">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="4babc-233">ユーザーを既存のサイトから新SharePointサイトにSharePointする方法は、次の方法で行います。</span><span class="sxs-lookup"><span data-stu-id="4babc-233">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="4babc-234">次のコマンドを実行して、ポータル起動ウェーブを指定します。</span><span class="sxs-lookup"><span data-stu-id="4babc-234">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="4babc-235">例:</span><span class="sxs-lookup"><span data-stu-id="4babc-235">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="4babc-236">完全な検証。</span><span class="sxs-lookup"><span data-stu-id="4babc-236">Complete validation.</span></span> <span data-ttu-id="4babc-237">リダイレクトがサービス全体で構成を完了するには、5 ~ 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-237">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="4babc-238">一時ページへのリダイレクトの手順</span><span class="sxs-lookup"><span data-stu-id="4babc-238">Steps for redirection to temporary page</span></span>

<span data-ttu-id="4babc-239">一時ページリダイレクトは、既存のポータルが存在しないSharePoint使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-239">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="4babc-240">ユーザーは、新しいモダン SharePointオンライン ポータルに対して、ステージ上の方法で指示されます。</span><span class="sxs-lookup"><span data-stu-id="4babc-240">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="4babc-241">ユーザーが起動されていないウェーブの場合、ユーザーは一時ページ (任意の URL) にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="4babc-241">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="4babc-242">次のコマンドを実行して、ポータル起動ウェーブを指定します。</span><span class="sxs-lookup"><span data-stu-id="4babc-242">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="4babc-243">例:</span><span class="sxs-lookup"><span data-stu-id="4babc-243">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="4babc-244">完全な検証。</span><span class="sxs-lookup"><span data-stu-id="4babc-244">Complete validation.</span></span> <span data-ttu-id="4babc-245">リダイレクトがサービス全体で構成を完了するには、5 ~ 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4babc-245">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="4babc-246">サイトでのポータルの起動を一時停止または再起動する</span><span class="sxs-lookup"><span data-stu-id="4babc-246">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="4babc-247">進行中のポータルの起動を一時停止し、今後のウェーブの進行を一時的に防止するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4babc-247">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="4babc-248">すべてのユーザーが古いサイトにリダイレクトされるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="4babc-248">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="4babc-249">一時停止されているポータルの起動を再開するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4babc-249">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="4babc-250">リダイレクトが復元されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="4babc-250">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="4babc-251">サイト上のポータルの起動を削除する</span><span class="sxs-lookup"><span data-stu-id="4babc-251">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="4babc-252">次のコマンドを実行して、サイトのスケジュール済みまたは進行中のポータル起動を削除します。</span><span class="sxs-lookup"><span data-stu-id="4babc-252">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="4babc-253">すべてのユーザーに対してリダイレクトが実行されなかろうと検証します。</span><span class="sxs-lookup"><span data-stu-id="4babc-253">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="4babc-254">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4babc-254">Learn more</span></span>

[<span data-ttu-id="4babc-255">オンラインでポータルの起動ロールアウト計画をSharePointする</span><span class="sxs-lookup"><span data-stu-id="4babc-255">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="4babc-256">コミュニケーション サイトを計画する</span><span class="sxs-lookup"><span data-stu-id="4babc-256">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
