---
title: グループ サービスのやり取り
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: グループ サービスのやり取り
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921026"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="dc0bb-103">グループ サービスのやり取り</span><span class="sxs-lookup"><span data-stu-id="dc0bb-103">Groups services interactions</span></span>

<span data-ttu-id="dc0bb-104">Microsoft 365 グループは、エンド ユーザーに接続されたエクスペリエンスを提供するために、Microsoft 365 プラットフォーム内の多数のサービスとワークロードに共通のファブリックを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="dc0bb-105">コアとなる Microsoft 365 グループは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="dc0bb-106">メンバーシップを管理する方法 (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="dc0bb-107">メッセージングと会話を行う場所 (Exchange メールボックス、Microsoft Teams、Yammer)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="dc0bb-108">ファイルを保存する場所 (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="dc0bb-109">スケジュールの予定表 (Exchange)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="dc0bb-110">メモをキャプチャするためのノートブック (OneNote)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="dc0bb-111">グループの作成時点では、他の多くのリソースもプロビジョニングされます。ただし、サービスから初めてアクセスするまで表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="dc0bb-112">グループ タスクを管理するためのボード (Planner)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="dc0bb-113">レポート用のワークスペース (Power BI)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="dc0bb-114">共有ビデオの領域 (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="dc0bb-115">共有フォームの領域 (フォーム)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="dc0bb-116">Microsoft 365 全体で、他のサービスは Microsoft 365 グループと対話して、グループ メンバーに追加の機能と機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="dc0bb-117">その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-117">Examples of this include:</span></span>

- <span data-ttu-id="dc0bb-118">Power Apps for apps</span><span class="sxs-lookup"><span data-stu-id="dc0bb-118">Power Apps for apps</span></span>
- <span data-ttu-id="dc0bb-119">ワークフローの Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc0bb-119">Power Automate for workflows</span></span>
- <span data-ttu-id="dc0bb-120">Web 上のプロジェクトとウォーターフォール ベースのプロジェクト管理のロードマップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="dc0bb-121">チャネル ベースの会話用の Teams</span><span class="sxs-lookup"><span data-stu-id="dc0bb-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="dc0bb-122">Yammerのコミュニティ向け情報</span><span class="sxs-lookup"><span data-stu-id="dc0bb-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="dc0bb-123">グループとのユーザー操作</span><span class="sxs-lookup"><span data-stu-id="dc0bb-123">User interactions with groups</span></span>

<span data-ttu-id="dc0bb-124">Microsoft 365 グループは、管理者とエンドユーザーの両方で、さまざまなインターフェイスから作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="dc0bb-125">管理エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="dc0bb-125">Administrative experiences</span></span>

<span data-ttu-id="dc0bb-126">管理者は、いくつかのワークロード管理センター、スクリプトをサポートするコマンド ライン インターフェイス、および Graph API を操作するカスタムビルド アプリから Microsoft 365 グループを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="dc0bb-127">この唯一の例外は、Yammerグループです。これは、web インターフェイス内からYammerする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="dc0bb-128">**関連する設定**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-128">**Related settings**</span></span>

<span data-ttu-id="dc0bb-129">グループ設定を管理できるさまざまな管理インターフェイスには、注意する必要がある複数の重複が存在します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="dc0bb-130">**Microsoft 365 管理センター**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="dc0bb-131">Microsoft 365 管理センターでは、所有者がゲストを追加できる機能と同様に、グループへのゲスト アクセスが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="dc0bb-132">この管理センターからグループに使用できる組織レベルのコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="dc0bb-133">**Azure AD 管理センター**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-133">**Azure AD admin center**</span></span>

<span data-ttu-id="dc0bb-134">Azure AD管理センターには、ユーザーがグループを作成するか、Azure ポータルで所有者を割り当てるか、有効期限と名前付けポリシーの設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="dc0bb-135">また、管理センターには、Microsoft 365 管理センター以外のゲストへの招待を制限する機能など、多数のゲスト招待制御手段が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="dc0bb-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-136">**SharePoint**</span></span>

<span data-ttu-id="dc0bb-137">SharePoint サイトは、所有者、メンバー、および訪問者のセキュリティ グループで作成され、最初の 2 つのサイトは Microsoft 365 グループのセキュリティ グループと一致します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="dc0bb-138">SharePoint Online サイトのメンバーシップは通常、関連付けられた Microsoft 365 グループによって管理されます。双方向の関係ではありません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="dc0bb-139">Microsoft 365 グループ レベルでのメンバーシップの変更は SharePoint に反映されます。ただし、SharePoint グループでメンバーシップが変更された場合、これは Microsoft 365 グループには反映されません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="dc0bb-140">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="dc0bb-140">User experiences</span></span>

<span data-ttu-id="dc0bb-141">エンド ユーザーは、Microsoft 365 内のいくつかのサービスからグループを作成し、他のユーザーはグループとのみ共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="dc0bb-142">次のサービスでは、エンド ユーザーによるグループの作成が可能です。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="dc0bb-143">Outlook Planner Project for the web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="dc0bb-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="dc0bb-144">**グループ作成の制限**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-144">**Restriction of group creation**</span></span>

<span data-ttu-id="dc0bb-145">チームの広がりを制御する一般的な方法は、作成できるユーザーを制限する方法です。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="dc0bb-146">これは、グループの作成を制限することでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="dc0bb-147">これにより、エンド ユーザーに必要になる可能性がある他のサービスからグループを作成する機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="dc0bb-148">Microsoft 365 グループは、一部のアプリやサービスからのグループの作成を制限する機能をサポートしていない一方で、他のアプリやサービスからのグループの作成を許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="dc0bb-149">グループ作成の制限のエクスペリエンスは、アプリとサービスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="dc0bb-150">アプリまたはサービス</span><span class="sxs-lookup"><span data-stu-id="dc0bb-150">App or service</span></span>|<span data-ttu-id="dc0bb-151">エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="dc0bb-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="dc0bb-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="dc0bb-152">Outlook</span></span>|<span data-ttu-id="dc0bb-153">**[ユーザー] ページ** の [新しいメニュー] から新しいグループ オプションが削除されました</span><span class="sxs-lookup"><span data-stu-id="dc0bb-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="dc0bb-154">Planner</span><span class="sxs-lookup"><span data-stu-id="dc0bb-154">Planner</span></span>|<span data-ttu-id="dc0bb-155">**新しいプラン** では、グループの作成がオフになっていることを説明し、既存のグループにプランを追加するオファーを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="dc0bb-156">Web およびロードマップのプロジェクト</span><span class="sxs-lookup"><span data-stu-id="dc0bb-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="dc0bb-157">**[グループの作成** ] メニューでは、グループの作成が制限され、既存のグループの使用を提案します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="dc0bb-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dc0bb-158">SharePoint</span></span>|<span data-ttu-id="dc0bb-159">グループに接続されていないチーム サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="dc0bb-160">Stream</span><span class="sxs-lookup"><span data-stu-id="dc0bb-160">Stream</span></span>|<span data-ttu-id="dc0bb-161">**[作成** ] メニューの下にグループ オプション **が表示されません**。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="dc0bb-162">Teams</span><span class="sxs-lookup"><span data-stu-id="dc0bb-162">Teams</span></span>|<span data-ttu-id="dc0bb-163">ユーザーは新しいグループを持つチームを作成することはできませんが、既存のグループを利用するチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="dc0bb-164">**[チームの作成]** ボタンが [グループからチームを作成 **する] に置き換えられる**。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="dc0bb-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="dc0bb-165">Yammer</span></span>|<span data-ttu-id="dc0bb-166">**グループの作成オプション** は、メインの [グループ/コミュニティ] ナビゲーションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="dc0bb-167">グループとのサービスのやり取り</span><span class="sxs-lookup"><span data-stu-id="dc0bb-167">Services interactions with groups</span></span>

<span data-ttu-id="dc0bb-168">さまざまな種類のグループ、グループの作成方法と管理方法、およびガバナンスに関する推奨事項については、「Microsoft 365 のグループ」ポスターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="dc0bb-169">[![グループ インフォグラフィックのサムネイル](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="dc0bb-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="dc0bb-171">次の表に、Microsoft 365 グループのさまざまなサービスとの対話の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="dc0bb-172">製品</span><span class="sxs-lookup"><span data-stu-id="dc0bb-172">Product</span></span>|<span data-ttu-id="dc0bb-173">機能</span><span class="sxs-lookup"><span data-stu-id="dc0bb-173">Features</span></span>|<span data-ttu-id="dc0bb-174">サービスを実行する</span><span class="sxs-lookup"><span data-stu-id="dc0bb-174">Does the service</span></span><br><span data-ttu-id="dc0bb-175">グループが存在しない場合</span><span class="sxs-lookup"><span data-stu-id="dc0bb-175">exist without a group?</span></span>|<span data-ttu-id="dc0bb-176">サービスを実行できる</span><span class="sxs-lookup"><span data-stu-id="dc0bb-176">Can the service</span></span><br><span data-ttu-id="dc0bb-177">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="dc0bb-177">create a group?</span></span>|<span data-ttu-id="dc0bb-178">を削除します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-178">Does deleting the</span></span><br><span data-ttu-id="dc0bb-179">インスタンスがグループを削除しますか?</span><span class="sxs-lookup"><span data-stu-id="dc0bb-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="dc0bb-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc0bb-180">Azure AD</span></span>|<span data-ttu-id="dc0bb-181">メンバーシップ、グループ コントロール、ゲスト</span><span class="sxs-lookup"><span data-stu-id="dc0bb-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="dc0bb-182">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-182">Yes</span></span>|<span data-ttu-id="dc0bb-183">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-183">Yes</span></span>|<span data-ttu-id="dc0bb-184">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-184">Yes</span></span>|
|<span data-ttu-id="dc0bb-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="dc0bb-185">Exchange</span></span>|<span data-ttu-id="dc0bb-186">予定表、メールボックス</span><span class="sxs-lookup"><span data-stu-id="dc0bb-186">Calendar, mailbox</span></span>|<span data-ttu-id="dc0bb-187">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-187">Yes</span></span>|<span data-ttu-id="dc0bb-188">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-188">Yes</span></span>|<span data-ttu-id="dc0bb-189">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-189">Yes</span></span>|
|<span data-ttu-id="dc0bb-190">フォーム</span><span class="sxs-lookup"><span data-stu-id="dc0bb-190">Forms</span></span>|<span data-ttu-id="dc0bb-191">フォーム</span><span class="sxs-lookup"><span data-stu-id="dc0bb-191">Form</span></span>|<span data-ttu-id="dc0bb-192">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-192">Yes</span></span>|<span data-ttu-id="dc0bb-193">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-193">No</span></span>|<span data-ttu-id="dc0bb-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-194">No</span></span>|
|<span data-ttu-id="dc0bb-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="dc0bb-195">OneNote</span></span>|<span data-ttu-id="dc0bb-196">ノートブック</span><span class="sxs-lookup"><span data-stu-id="dc0bb-196">Notebook</span></span>|<span data-ttu-id="dc0bb-197">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-197">Yes</span></span>|<span data-ttu-id="dc0bb-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-198">No</span></span>|<span data-ttu-id="dc0bb-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-199">No</span></span>|
|<span data-ttu-id="dc0bb-200">Planner</span><span class="sxs-lookup"><span data-stu-id="dc0bb-200">Planner</span></span>|<span data-ttu-id="dc0bb-201">タスク ボード</span><span class="sxs-lookup"><span data-stu-id="dc0bb-201">Task board</span></span>|<span data-ttu-id="dc0bb-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-202">No</span></span>|<span data-ttu-id="dc0bb-203">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-203">Yes</span></span>|<span data-ttu-id="dc0bb-204">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-204">Yes</span></span>|
|<span data-ttu-id="dc0bb-205">Power Apps アプリ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-205">Power Apps app</span></span>|<span data-ttu-id="dc0bb-206">アプリ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-206">App</span></span>|<span data-ttu-id="dc0bb-207">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-207">Yes</span></span>|<span data-ttu-id="dc0bb-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-208">No</span></span>|<span data-ttu-id="dc0bb-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-209">No</span></span>|
|<span data-ttu-id="dc0bb-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc0bb-210">Power Automate</span></span>|<span data-ttu-id="dc0bb-211">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="dc0bb-211">Workflow</span></span>|<span data-ttu-id="dc0bb-212">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-212">Yes</span></span>|<span data-ttu-id="dc0bb-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-213">No</span></span>|<span data-ttu-id="dc0bb-214">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-214">No</span></span>|
|<span data-ttu-id="dc0bb-215">Power BI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-215">Power BI (classic)</span></span>|<span data-ttu-id="dc0bb-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="dc0bb-216">Workspace</span></span>|<span data-ttu-id="dc0bb-217">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-217">No</span></span>|<span data-ttu-id="dc0bb-218">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-218">Yes</span></span>|<span data-ttu-id="dc0bb-219">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-219">Yes</span></span>|
|<span data-ttu-id="dc0bb-220">Power BI (新しい)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-220">Power BI (new)</span></span>|<span data-ttu-id="dc0bb-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="dc0bb-221">Workspace</span></span>|<span data-ttu-id="dc0bb-222">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-222">Yes</span></span>|<span data-ttu-id="dc0bb-223">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-223">No</span></span>|<span data-ttu-id="dc0bb-224">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-224">Yes</span></span>|
|<span data-ttu-id="dc0bb-225">Project for the web</span><span class="sxs-lookup"><span data-stu-id="dc0bb-225">Project for the web</span></span>|<span data-ttu-id="dc0bb-226">Project plan</span><span class="sxs-lookup"><span data-stu-id="dc0bb-226">Project plan</span></span>|<span data-ttu-id="dc0bb-227">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-227">Yes</span></span>|<span data-ttu-id="dc0bb-228">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-228">Yes</span></span>|<span data-ttu-id="dc0bb-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-229">No</span></span>|
|<span data-ttu-id="dc0bb-230">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-230">Roadmap</span></span>|<span data-ttu-id="dc0bb-231">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-231">Roadmap</span></span>|<span data-ttu-id="dc0bb-232">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-232">Yes</span></span>|<span data-ttu-id="dc0bb-233">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-233">Yes</span></span>|<span data-ttu-id="dc0bb-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-234">No</span></span>|
|<span data-ttu-id="dc0bb-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dc0bb-235">SharePoint</span></span>|<span data-ttu-id="dc0bb-236">Site</span><span class="sxs-lookup"><span data-stu-id="dc0bb-236">Site</span></span>|<span data-ttu-id="dc0bb-237">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-237">Yes</span></span>|<span data-ttu-id="dc0bb-238">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-238">Yes</span></span>|<span data-ttu-id="dc0bb-239">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-239">Yes</span></span>|
|<span data-ttu-id="dc0bb-240">Stream</span><span class="sxs-lookup"><span data-stu-id="dc0bb-240">Stream</span></span>|<span data-ttu-id="dc0bb-241">チャネル、ビデオ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-241">Channel, video</span></span>|<span data-ttu-id="dc0bb-242">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-242">Yes</span></span>|<span data-ttu-id="dc0bb-243">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-243">Yes</span></span>|<span data-ttu-id="dc0bb-244">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-244">Yes</span></span>|
|<span data-ttu-id="dc0bb-245">Teams</span><span class="sxs-lookup"><span data-stu-id="dc0bb-245">Teams</span></span>|<span data-ttu-id="dc0bb-246">チーム</span><span class="sxs-lookup"><span data-stu-id="dc0bb-246">Team</span></span>|<span data-ttu-id="dc0bb-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-247">No</span></span>|<span data-ttu-id="dc0bb-248">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-248">Yes</span></span>|<span data-ttu-id="dc0bb-249">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-249">Yes</span></span>|
|<span data-ttu-id="dc0bb-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="dc0bb-250">Yammer</span></span>|<span data-ttu-id="dc0bb-251">Group</span><span class="sxs-lookup"><span data-stu-id="dc0bb-251">Group</span></span>|<span data-ttu-id="dc0bb-252">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-252">Yes</span></span>|<span data-ttu-id="dc0bb-253">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-253">Yes</span></span>|<span data-ttu-id="dc0bb-254">はい</span><span class="sxs-lookup"><span data-stu-id="dc0bb-254">Yes</span></span>|

<span data-ttu-id="dc0bb-255">上記の表では、Microsoft 365 サービスとのグループ操作の概要を示しますが、理解する必要があるニュアンスや重要な点が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="dc0bb-256">次のセクションでは、特定のワークロードとグループとのやり取りについて詳しい説明を行います。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="dc0bb-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc0bb-257">Azure AD</span></span>

<span data-ttu-id="dc0bb-258">Azure ADは、Microsoft 365 全体で基になる ID 管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="dc0bb-259">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-260">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-260">Group membership</span></span>
- <span data-ttu-id="dc0bb-261">名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="dc0bb-261">Naming policy</span></span>
- <span data-ttu-id="dc0bb-262">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="dc0bb-262">Expiration policy</span></span>
- <span data-ttu-id="dc0bb-263">ゲスト</span><span class="sxs-lookup"><span data-stu-id="dc0bb-263">Guests</span></span>
- <span data-ttu-id="dc0bb-264">グループ作成の制限</span><span class="sxs-lookup"><span data-stu-id="dc0bb-264">Restriction of Group creation</span></span>

<span data-ttu-id="dc0bb-265">**Azure はAD作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="dc0bb-266">はい、Microsoft 365 グループは、Azure AD PowerShell または Graph API を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="dc0bb-267">**Azure はAD存在しませんか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="dc0bb-268">はい、Azure ADは、Microsoft 365 グループとは関係がない多数のサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="dc0bb-269">各 Microsoft 365 グループは、Azure サーバーのオブジェクトとしてAD。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="dc0bb-270">**グループごとに複数の Azure ADを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="dc0bb-271">いいえ、Azure サーバーのインスタンスは 1 AD。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="dc0bb-272">**Azure ADグループに関連付け可能ですか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="dc0bb-273">はい、Azure ADは、グループ メンバーシップ サービスを提供する基になるプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="dc0bb-274">**Azure はADグループとの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-275">いいえ、Azure ADは、グループが存在する基になるプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="dc0bb-276">**インスタンスを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="dc0bb-277">Azure ADグループを削除すると、関連するグループ関連のサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="dc0bb-278">Teams</span><span class="sxs-lookup"><span data-stu-id="dc0bb-278">Teams</span></span>

<span data-ttu-id="dc0bb-279">Teams は、さまざまな Microsoft およびサード パーティのサービスと対話するための単一のインターフェイスを提供することで、コラボレーションを強化することを目的としたチャット中心のワークスペースです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="dc0bb-280">既定では、チームが作成されると、Microsoft 365 グループに関連付けられているメールボックスと予定表は、Exchange のグローバル アドレス一覧と Outlook の両方から非表示になります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="dc0bb-281">ユーザーが同じ Microsoft 365 グループで Outlook と Teams の両方を使用する場合は、管理者が手動で上書きできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="dc0bb-282">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-283">会話</span><span class="sxs-lookup"><span data-stu-id="dc0bb-283">Conversations</span></span>
- <span data-ttu-id="dc0bb-284">チャネル&タブ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-284">Channels & tabs</span></span>
- <span data-ttu-id="dc0bb-285">会議</span><span class="sxs-lookup"><span data-stu-id="dc0bb-285">Meetings</span></span>

<span data-ttu-id="dc0bb-286">**Teams はグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="dc0bb-287">はい、新しいチームを作成すると、新しい Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="dc0bb-288">現在存在しない既存のグループに対してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="dc0bb-289">**チームはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="dc0bb-290">いいえ、グループなしでチームが存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="dc0bb-291">**グループごとに複数のチームを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="dc0bb-292">いいえ、チームとグループの関係は 1:1 です。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="dc0bb-293">**チームを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-294">いいえ、チーム自体は 1 つのグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="dc0bb-295">**チームとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-296">いいえ、チームは、最初に関連付けられたグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="dc0bb-297">**チームを削除すると、グループは削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="dc0bb-298">はい、Microsoft Teams でチームを削除すると、グループ、グループに関連付けられたサービス、およびコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="dc0bb-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="dc0bb-299">Exchange</span></span>

<span data-ttu-id="dc0bb-300">Exchange Online は、メッセージング、予定表、連絡先、および関連する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="dc0bb-301">グループのコンテキストでは、サービス インスタンス全体とは対照的に、1 つのリソースだけが関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="dc0bb-302">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-303">メールボックスと予定表</span><span class="sxs-lookup"><span data-stu-id="dc0bb-303">Mailbox and calendar</span></span>
- <span data-ttu-id="dc0bb-304">すべてのグループ メンバーにメールを送信する機能</span><span class="sxs-lookup"><span data-stu-id="dc0bb-304">Ability to email all Group members</span></span>
- <span data-ttu-id="dc0bb-305">電子情報開示を目的として Teams チャネルの会話を保存する、Planner のコメント</span><span class="sxs-lookup"><span data-stu-id="dc0bb-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="dc0bb-306">**Exchange はグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="dc0bb-307">はい、Exchange Online 管理センターと Outlook からグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="dc0bb-308">Exchange 配布リストを Microsoft 365 グループに変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="dc0bb-309">**Exchange はグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="dc0bb-310">はい、Exchange Online は、グループの関連付けを行わずに、共有メールボックスや予定表を含む多くのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="dc0bb-311">**グループごとに Exchange メールボックスまたは予定表のインスタンスが複数あるか。**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="dc0bb-312">いいえ、グループに使用できる Exchange Online メールボックスと予定表は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="dc0bb-313">**Exchange メールボックスと予定表を複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-314">いいえ、メールボックスと予定表には、グループとの 1:1 の関係があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="dc0bb-315">メールボックスを他のユーザーまたはグループと共有することもできますが、サービスの関連付けは確立されません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="dc0bb-316">**Exchange メールボックスまたは予定表とグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-317">いいえ、メールボックスと予定表を別のグループに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="dc0bb-318">ただし、Outlook 内で、またはサード パーティ製のツールを使用して、あるメールボックスから別のメールボックスにコンテンツを移動できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="dc0bb-319">**メールボックスを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="dc0bb-320">はい、Exchange でメールボックスを削除すると、グループに関連付けられたサービスとコンテンツと同様にグループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="dc0bb-321">フォーム</span><span class="sxs-lookup"><span data-stu-id="dc0bb-321">Forms</span></span>

<span data-ttu-id="dc0bb-322">フォームは、Web ベースのアンケートとクイズを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="dc0bb-323">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="dc0bb-324">フォームの所有権</span><span class="sxs-lookup"><span data-stu-id="dc0bb-324">Ownership of forms</span></span>

<span data-ttu-id="dc0bb-325">**Forms はグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="dc0bb-326">いいえ、Forms はグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="dc0bb-327">**フォームはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="dc0bb-328">はい、アンケートやクイズはエンドユーザーのアカウントで直接作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="dc0bb-329">**グループごとに複数のフォームを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="dc0bb-330">はい、グループに複数のフォームが関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="dc0bb-331">**フォームを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-332">いいえ、フォームは 1 つのグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="dc0bb-333">**フォームとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-334">いいえ、フォームがグループに関連付けられたら (直接作成されるか、個人から転送された所有権のいずれか)、別のグループに移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="dc0bb-335">**フォームを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="dc0bb-336">いいえ、Forms インターフェイスからグループを削除できるのは、個々のフォームのみです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="dc0bb-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="dc0bb-337">OneNote</span></span>

<span data-ttu-id="dc0bb-338">OneNote はデジタル ノートブック アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="dc0bb-339">グループで作成された OneNote ノートブックは、グループに接続されたサービスではなく、関連付けられた SharePoint サイト内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="dc0bb-340">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="dc0bb-341">共有ノートブック (グループに関連付けられた SharePoint ライブラリに保存)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="dc0bb-342">**OneNote でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="dc0bb-343">いいえ、OneNote アプリケーションはグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="dc0bb-344">**OneNote ノートブックはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="dc0bb-345">はい、ノートブックは OneDrive または他の共有場所で直接作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="dc0bb-346">**グループごとに複数の OneNote ノートブックを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="dc0bb-347">はい、ノートブックは既定で作成され、他のユーザーも追加できます。ただし、グループ関連サービスから OneNote へのリンクは常に既定のノートブックに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="dc0bb-348">**OneNote ノートブックを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-349">いいえ、ノートブックはグループ関連の SharePoint サイト ライブラリに格納され、さまざまなインターフェイスからリンクされます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="dc0bb-350">ただし、個人と共有できるのと同じ方法で他のグループと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="dc0bb-351">**ノートブックとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-352">いいえ、ノートブック自体はグループに関連付けられているので、他のグループ接続サービスから直接アクセスすることもできますが、OneNote アプリケーション内でコンテンツをノートブック間で移動できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="dc0bb-353">**ノートブックを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="dc0bb-354">ただし、OneNote ノートブックが削除された場合は、グループ関連サービスの一部にリンクが壊れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="dc0bb-355">Planner</span><span class="sxs-lookup"><span data-stu-id="dc0bb-355">Planner</span></span>

<span data-ttu-id="dc0bb-356">Planner は、軽量なグループ タスク管理サービスです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="dc0bb-357">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="dc0bb-358">グループ タスクを管理するためのボード</span><span class="sxs-lookup"><span data-stu-id="dc0bb-358">Board for managing group tasks</span></span>

<span data-ttu-id="dc0bb-359">**Planner はグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="dc0bb-360">はい、プランの作成によって新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="dc0bb-361">**Planner ボードはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="dc0bb-362">いいえ、プランはグループに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="dc0bb-363">**グループごとに複数のプランを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="dc0bb-364">はい、グループごとに複数のプランを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="dc0bb-365">**プランを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-366">いいえ、プランはグループ メンバーシップのみに依存してアクセスを決定します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="dc0bb-367">**プランとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-368">ただし、プランをコピーすると新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="dc0bb-369">他のアプリケーションによって作成されたグループは、ユーザーの Planner に自動的に表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="dc0bb-370">最初にボードにアクセスするには、Outlook などの別のグループ ベースのインターフェイスからボードを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="dc0bb-371">**プランを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="dc0bb-372">はい、プランを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="dc0bb-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="dc0bb-373">Power Apps</span></span>

<span data-ttu-id="dc0bb-374">Power Apps は、コードのないアプリ開発用のキャンバスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="dc0bb-375">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-376">アプリは、実行および変更するグループと共有できます</span><span class="sxs-lookup"><span data-stu-id="dc0bb-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="dc0bb-377">**Power Apps でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="dc0bb-378">いいえ、Power Apps は Microsoft 365 グループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="dc0bb-379">**Power Apps はグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="dc0bb-380">はい、アプリは Power Apps 内で作成し、共有または公開されるまでクリエイター アカウント内に存在できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="dc0bb-381">**グループごとに複数のアプリを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="dc0bb-382">はい、複数のアプリがグループと共有されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="dc0bb-383">**アプリを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-384">はい、アプリは複数のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="dc0bb-385">**アプリとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-386">はい、Power Apps と Microsoft 365 グループの関連付けは共有のみ行うので、アプリは作成者と引き続き存在します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc0bb-387">[アプリを共有するには、セキュリティを有効にする必要があります](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="dc0bb-388">**アプリを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="dc0bb-389">いいえ、アプリはグループと共有される以外のグループに接続されていません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="dc0bb-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc0bb-390">Power Automate</span></span>

<span data-ttu-id="dc0bb-391">Power Automation (以前は Microsoft Flow と呼ばれる) は、ワークフローとオートメーション サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="dc0bb-392">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="dc0bb-393">ワークフローは、実行および変更するグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="dc0bb-394">**Power Automate でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="dc0bb-395">いいえ、Power Automate は、Microsoft 365 グループに関連付けられているコンテキストでは作成できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="dc0bb-396">ただし、Azure AD セキュリティ グループの作成や Microsoft 365 グループのメンバーシップの更新など、さまざまな操作を実行するフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="dc0bb-397">**フローはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="dc0bb-398">はい、フローは Power Automate 内で作成し、共有または公開されるまで作成者アカウント内に存在できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="dc0bb-399">**グループごとに複数のフローを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="dc0bb-400">はい、複数のフローがグループと共有されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="dc0bb-401">**フローを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-402">はい、フローは複数のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="dc0bb-403">**フローとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-404">はい、Power Automate と Microsoft 365 グループの関連付けは共有のみ行うので、フローは作成者と引き続き存在します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="dc0bb-405">**フローを削除すると、グループは削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="dc0bb-406">いいえ、Power Apps と同様に、フローはグループと共有される以外のグループに接続されていません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="dc0bb-407">Power BI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-407">Power BI (classic)</span></span>

<span data-ttu-id="dc0bb-408">Power BI は、対話型のデータ駆動型ダッシュボードとレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="dc0bb-409">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="dc0bb-410">データレポート</span><span class="sxs-lookup"><span data-stu-id="dc0bb-410">Data reporting</span></span>

<span data-ttu-id="dc0bb-411">**Power BI でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="dc0bb-412">はい、クラシック ワークスペースを作成すると、Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="dc0bb-413">**Power BI クラシック ワークスペースはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="dc0bb-414">いいえ [、Power BI のクラシック ワークスペースはグループに関連付けられている必要があります](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="dc0bb-415">**グループごとに複数の Power BI ワークスペースを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="dc0bb-416">いいえ、クラシック ワークスペースとグループの関係は 1:1 です。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="dc0bb-417">**ワークスペースを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-418">技術的にはいいえ、従来のワークスペースはグループと一緒に作成しますが、コンテンツはグループの外部でユーザーおよびセキュリティ グループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="dc0bb-419">**ワークスペースとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="dc0bb-420">いいえ、従来のワークスペース自体はグループに関連付けられているが、コンテンツは Power BI インターフェイス内で、またはコンテンツをローカルにエクスポートすることで、あるワークスペースから別のワークスペースに移動できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="dc0bb-421">**ワークスペースを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="dc0bb-422">はい、Power BI でワークスペースを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="dc0bb-423">Power BI (新しい)</span><span class="sxs-lookup"><span data-stu-id="dc0bb-423">Power BI (new)</span></span>

<span data-ttu-id="dc0bb-424">Power BI は、対話型のデータ駆動型ダッシュボードとレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="dc0bb-425">Power BI で新しいワークスペースを作成しても Microsoft 365 グループは作成されませんが、他の方法でグループを作成すると、Power BI に新しい (クラシックではない) ワークスペースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="dc0bb-426">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="dc0bb-427">データレポート</span><span class="sxs-lookup"><span data-stu-id="dc0bb-427">Data reporting</span></span>

<span data-ttu-id="dc0bb-428">**Power BI でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="dc0bb-429">いいえ、新しい Power BI インターフェイスから Microsoft 365 グループを作成する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="dc0bb-430">**新しい Power BI ワークスペースはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="dc0bb-431">はい、Microsoft 365 グループに関連付けされていないレポートとワークスペースを Power BI で作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="dc0bb-432">**グループごとに複数のワークスペースを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="dc0bb-433">はい [、Power BI によって作成された複数のワークスペースを 1 つのグループと共有できます](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="dc0bb-434">**ワークスペースを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-435">いいえ、Power BI によって作成されたワークスペースは、1 つのグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="dc0bb-436">**ワークスペースとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="dc0bb-437">さあ何とも言えません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-437">Yes and no.</span></span> <span data-ttu-id="dc0bb-438">Power BI によって作成されたワークスペースは、一度に 1 つのグループにのみ関連付けできますが、いつでも関連付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="dc0bb-439">グループによって Power BI で作成されたワークスペースは、そのグループに完全に関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="dc0bb-440">**ワークスペースを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="dc0bb-441">はい、Power BI でワークスペースを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="dc0bb-442">Project for the web</span><span class="sxs-lookup"><span data-stu-id="dc0bb-442">Project for the web</span></span>

<span data-ttu-id="dc0bb-443">Project for the Web では、プロジェクト 計画、ガント チャート、ロードマップを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="dc0bb-444">グループに提供される主な機能。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-444">Key features provided to groups.</span></span>

- <span data-ttu-id="dc0bb-445">プロジェクト計画</span><span class="sxs-lookup"><span data-stu-id="dc0bb-445">Project plans</span></span>

<span data-ttu-id="dc0bb-446">**Project for the Web はグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="dc0bb-447">はい、Web 用 Project から直接新しい Microsoft 365 グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="dc0bb-448">**グループのないプロジェクトは存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="dc0bb-449">はい、プロジェクトは Microsoft 365 グループに関連付けずに存在することができますが、タスクの割り当てにはグループの関連付けを必要とします。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="dc0bb-450">**グループごとに複数のプロジェクトを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="dc0bb-451">はい、1 つのグループに複数のプロジェクトを接続できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="dc0bb-452">**プロジェクトを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-453">いいえ、プロジェクトは 1 つのグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="dc0bb-454">**プロジェクトとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-455">いいえ、グループとの関連付けを確立すると、変更できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="dc0bb-456">**プロジェクトを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="dc0bb-457">いいえ、Project for the web でプロジェクトを削除すると、グループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="dc0bb-458">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-458">Roadmap</span></span>

<span data-ttu-id="dc0bb-459">ロードマップは、Project for the Web および Project Online を使用してプロジェクト ロードマップを作成する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="dc0bb-460">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-461">プロジェクトのロードマップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-461">Project roadmaps</span></span>

<span data-ttu-id="dc0bb-462">**ロードマップでグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="dc0bb-463">はい、ロードマップから直接新しい Microsoft 365 グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="dc0bb-464">**ロードマップはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="dc0bb-465">はい、ロードマップは Microsoft 365 グループに関連付けずに存在することができますが、ロードマップを共有するにはグループの関連付けを必要とします。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="dc0bb-466">**グループごとに複数のロードマップを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="dc0bb-467">はい、複数のロードマップを 1 つのグループに接続できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="dc0bb-468">**ロードマップを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-469">いいえ、ロードマップは 1 つのグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="dc0bb-470">**ロードマップとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="dc0bb-471">いいえ、グループとの関連付けを確立すると、変更できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="dc0bb-472">**ロードマップを削除すると、グループは削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="dc0bb-473">いいえ、ロードマップを削除すると、グループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="dc0bb-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dc0bb-474">SharePoint</span></span>

<span data-ttu-id="dc0bb-475">SharePoint は、さまざまな Microsoft 365 サービスのストレージ サービスを提供する Web ベースのコンテンツ管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="dc0bb-476">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-477">ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-477">Document library</span></span>
- <span data-ttu-id="dc0bb-478">OneNote ノートブックのストレージ用ライブラリ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="dc0bb-479">Teams Wiki ファイルのストレージ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="dc0bb-480">**SharePoint でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="dc0bb-481">はい、SharePoint でチーム サイトを作成すると、既定で Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="dc0bb-482">グループを作成し、必要に応じて既存のサイトのチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="dc0bb-483">**SharePoint サイトはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="dc0bb-484">はい、SharePoint には、グループに関連付けされていないサービスや、通信サイトやハブ サイトなどのサイトが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="dc0bb-485">**グループごとに複数のサイトを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="dc0bb-486">いいえ、グループごとに 1 つのサイトしか使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="dc0bb-487">Teams のプライベート チャネルでは、グループに接続されていない追加のサイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="dc0bb-488">**サイトを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-489">技術的にはいいえですが、サイトはグループで作成されますが、コンテンツは他のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="dc0bb-490">**サイトとグループの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="dc0bb-491">いいえ、サイト自体はグループに関連付けられているが、コンテンツを SharePoint インターフェイス内のサイト間で移動したり、ローカルでコンテンツをエクスポートしたり、サードパーティ製のツールを使用したりして移動できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="dc0bb-492">**サイトを削除すると、グループが削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="dc0bb-493">はい、SharePoint でサイトを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="dc0bb-494">Stream</span><span class="sxs-lookup"><span data-stu-id="dc0bb-494">Stream</span></span>

<span data-ttu-id="dc0bb-495">Microsoft Stream は、ビデオ ホスティングと共有プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="dc0bb-496">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-497">ビデオ ストレージ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-497">Video storage</span></span>
- <span data-ttu-id="dc0bb-498">Teams 会議の記録</span><span class="sxs-lookup"><span data-stu-id="dc0bb-498">Teams meeting recording</span></span>
- <span data-ttu-id="dc0bb-499">ビデオ チャネル</span><span class="sxs-lookup"><span data-stu-id="dc0bb-499">Video channels</span></span>

<span data-ttu-id="dc0bb-500">**Stream でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="dc0bb-501">はい、Stream から直接新しい Microsoft 365 グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="dc0bb-502">**Stream はグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="dc0bb-503">はい、ビデオ チャネルとビデオは、グループに関連付けずに Stream に存在できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="dc0bb-504">**グループごとに複数のビデオとチャネルを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="dc0bb-505">はい、各グループに複数のビデオとチャネルを含めできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="dc0bb-506">**ビデオまたはチャネルを複数のグループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="dc0bb-507">はい、ビデオまたはチャネルがグループで作成されている間は、他のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="dc0bb-508">**グループとの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="dc0bb-509">はい、いいえ。Stream のビデオは元のアップアップロード者または会議レコーダーによって所有されます。そのため、どのグループにも関連付け可能ですが、ビデオ チャネルは、最初に作成されたグループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="dc0bb-510">**ビデオまたはチャネルを削除すると、グループは削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="dc0bb-511">いいえ、ビデオやチャネルを削除してもグループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="dc0bb-512">ただし、Stream でグループ自体を削除すると、実際のビデオを除き、グループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="dc0bb-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="dc0bb-513">Yammer</span></span>

<span data-ttu-id="dc0bb-514">Yammerは、組織内および組織間のコミュニティの関与を促進するように設計されたエンタープライズソーシャル プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="dc0bb-515">グループ内にコミュニティ (以前は "グループ" と呼ばれる) を作成Yammerメールボックスを作成しますが、現時点では、これは使用されません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="dc0bb-516">グループに関連付けられている Microsoft 365 グループYammer、Microsoft Teams のチームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="dc0bb-517">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="dc0bb-518">会話エリア</span><span class="sxs-lookup"><span data-stu-id="dc0bb-518">Conversation area</span></span>

<span data-ttu-id="dc0bb-519">**Microsoft 365 Yammer作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="dc0bb-520">はい、Yammer で新しいグループを作成すると、プラットフォームが接続され、ユーザーがグループを作成できる場合は、新しい Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="dc0bb-521">関連Yammer Microsoft 365 グループを持つグループは、ユーザー自身以外のインターフェイスまたはサービスYammerできません。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="dc0bb-522">**Microsoft 365 Yammerグループが存在しない場合、そのグループは存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="dc0bb-523">はい、Microsoft 365 グループをYammerグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="dc0bb-524">Yammer プラットフォームが Microsoft 365 グループに接続されていない場合、またはユーザーが Microsoft 365 グループを作成できない場合、Yammer グループは Microsoft 365 グループの関連付けなしで作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="dc0bb-525">**Microsoft 365 グループごとに複数Yammerグループを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="dc0bb-526">いいえ、グループと Microsoft 365 Yammerの関係は 1:1 です。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="dc0bb-527">**1 つのグループYammer複数の Microsoft 365 グループに関連付けできますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="dc0bb-528">いいえ、Yammerグループは単一の Microsoft 365 グループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="dc0bb-529">投稿を他のグループと共有したり、他のグループYammerできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="dc0bb-530">**Microsoft 365 Yammerグループとの関連付けを変更できますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="dc0bb-531">いいえ、Yammerグループは、最初に関連付けられた Microsoft 365 グループにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="dc0bb-532">**グループを削除Yammer Microsoft 365 グループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="dc0bb-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="dc0bb-533">はい、グループを削除すると、Yammer関連する Microsoft グループとグループ関連のサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc0bb-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc0bb-534">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc0bb-534">Related topics</span></span>

[<span data-ttu-id="dc0bb-535">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="dc0bb-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="dc0bb-536">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="dc0bb-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)