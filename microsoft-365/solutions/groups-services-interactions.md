---
title: グループサービスの相互作用
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
description: グループサービスの相互作用
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613228"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="ea930-103">グループサービスの相互作用</span><span class="sxs-lookup"><span data-stu-id="ea930-103">Groups services interactions</span></span>

<span data-ttu-id="ea930-104">Microsoft 365 グループは、Microsoft 365 プラットフォーム内のさまざまなサービスとワークロードに共通の fabric を提供して、エンドユーザー向けの接続性を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ea930-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="ea930-105">中核となるのは、Microsoft 365 グループが存在するためです。次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="ea930-106">メンバーシップを管理する方法 (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ea930-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="ea930-107">メッセージングと会話を行う場所 (Exchange メールボックス、Microsoft Teams、Yammer)</span><span class="sxs-lookup"><span data-stu-id="ea930-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="ea930-108">ファイルを保存する場所 (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="ea930-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="ea930-109">スケジュール設定用の予定表 (Exchange)</span><span class="sxs-lookup"><span data-stu-id="ea930-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="ea930-110">ノートをキャプチャするためのノートブック (OneNote)</span><span class="sxs-lookup"><span data-stu-id="ea930-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="ea930-111">グループの作成時点では、次のようないくつかのリソースもプロビジョニングされていますが、サービスから初めてアクセスしたときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="ea930-112">グループタスクを管理するためのボード (プランナー)</span><span class="sxs-lookup"><span data-stu-id="ea930-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="ea930-113">レポート用のワークスペース (Power BI)</span><span class="sxs-lookup"><span data-stu-id="ea930-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="ea930-114">共有ビデオの領域 (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="ea930-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="ea930-115">共有フォームの領域 (フォーム)</span><span class="sxs-lookup"><span data-stu-id="ea930-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="ea930-116">Microsoft 365 では、他のサービスが Microsoft 365 グループと対話して、グループメンバーに追加の機能を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="ea930-117">この例には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="ea930-117">Examples of this include:</span></span>

- <span data-ttu-id="ea930-118">アプリ用のパワーアプリ</span><span class="sxs-lookup"><span data-stu-id="ea930-118">Power Apps for apps</span></span>
- <span data-ttu-id="ea930-119">ワークフローの電源自動化</span><span class="sxs-lookup"><span data-stu-id="ea930-119">Power Automate for workflows</span></span>
- <span data-ttu-id="ea930-120">Web 上のプロジェクトとウォーターフォールベースのプロジェクト管理のロードマップ</span><span class="sxs-lookup"><span data-stu-id="ea930-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="ea930-121">チャネルベースの会話の Teams</span><span class="sxs-lookup"><span data-stu-id="ea930-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="ea930-122">関心のあるコミュニティの Yammer</span><span class="sxs-lookup"><span data-stu-id="ea930-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="ea930-123">グループを使用したユーザー操作</span><span class="sxs-lookup"><span data-stu-id="ea930-123">User interactions with groups</span></span>

<span data-ttu-id="ea930-124">Microsoft 365 グループは、管理者とエンドユーザーの両方から、さまざまなインターフェイスから作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="ea930-125">管理者エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ea930-125">Administrative experiences</span></span>

<span data-ttu-id="ea930-126">管理者は、いくつかのワークロード管理センター、スクリプトをサポートするコマンドラインインターフェイス、および Graph API と対話するカスタムのアプリを、Microsoft 365 グループの作成と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="ea930-127">唯一の例外は Yammer グループで、Yammer の web インターフェイスから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="ea930-128">**関連する設定**</span><span class="sxs-lookup"><span data-stu-id="ea930-128">**Related settings**</span></span>

<span data-ttu-id="ea930-129">グループ設定を管理できるさまざまな管理インターフェイスでは、いくつかの重なりがあり、注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="ea930-130">**Microsoft 365 管理センター**</span><span class="sxs-lookup"><span data-stu-id="ea930-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="ea930-131">Microsoft 365 管理センターでは、グループへのゲストアクセスは既定で有効になっており、ゲストの追加を所有者に許可することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="ea930-132">この管理センターから、グループに対して使用可能なその他の組織レベルの制御はありません。</span><span class="sxs-lookup"><span data-stu-id="ea930-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="ea930-133">**Azure AD 管理センター**</span><span class="sxs-lookup"><span data-stu-id="ea930-133">**Azure AD admin center**</span></span>

<span data-ttu-id="ea930-134">Azure AD 管理センターでは、ユーザーが Azure ポータルでグループを作成することも、所有者を割り当てることも、有効期限と名前付けポリシーの設定に関する制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="ea930-135">管理センターでは、所有者以外がゲストを招待できるかどうかを制限するなど、Microsoft 365 管理センターの機能を超えた多くのゲスト招待制御手段も提供されています。</span><span class="sxs-lookup"><span data-stu-id="ea930-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="ea930-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="ea930-136">**SharePoint**</span></span>

<span data-ttu-id="ea930-137">SharePoint サイトは、Owner、Member、およびビジタの各セキュリティグループを使用して作成され、最初の2つは対応する Microsoft 365 グループに一致します。</span><span class="sxs-lookup"><span data-stu-id="ea930-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="ea930-138">SharePoint Online サイトのメンバーシップは、通常、関連付けられた Microsoft 365 グループによって管理されていますが、双方向リレーションシップではありません。</span><span class="sxs-lookup"><span data-stu-id="ea930-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="ea930-139">Microsoft 365 グループレベルのメンバーシップに対する変更は、SharePoint に反映されますが、SharePoint グループでメンバーシップが変更されても、Microsoft 365 グループには反映されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="ea930-140">ユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ea930-140">User experiences</span></span>

<span data-ttu-id="ea930-141">エンドユーザーは、Microsoft 365 内のいくつかのサービスからグループを作成できます。また、他のユーザーはグループとのみ共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="ea930-142">次のサービスを使用すると、エンドユーザーによるグループの作成が可能になります。</span><span class="sxs-lookup"><span data-stu-id="ea930-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="ea930-143">Web SharePoint Stream の Outlook Planner プロジェクト Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="ea930-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="ea930-144">**グループの作成の制限**</span><span class="sxs-lookup"><span data-stu-id="ea930-144">**Restriction of group creation**</span></span>

<span data-ttu-id="ea930-145">チームの増加を制御するための一般的な方法は、ユーザーが作成できるユーザーを制限することです。</span><span class="sxs-lookup"><span data-stu-id="ea930-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="ea930-146">これを行うには、グループの作成を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="ea930-147">これにより、エンドユーザーが必要になる可能性のある他のサービスからグループを作成する機能が影響を受けることになります。</span><span class="sxs-lookup"><span data-stu-id="ea930-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="ea930-148">Microsoft 365 グループでは、一部のアプリまたはサービスからのグループの作成を制限する機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ea930-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="ea930-149">グループ作成の制限の効果は、アプリとサービスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ea930-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="ea930-150">アプリまたはサービス</span><span class="sxs-lookup"><span data-stu-id="ea930-150">App or service</span></span>|<span data-ttu-id="ea930-151">エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ea930-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="ea930-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="ea930-152">Outlook</span></span>|<span data-ttu-id="ea930-153">[ユーザー] ページの [新規作成] メニューから [**新しいグループ**] オプションが削除されている</span><span class="sxs-lookup"><span data-stu-id="ea930-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="ea930-154">Planner</span><span class="sxs-lookup"><span data-stu-id="ea930-154">Planner</span></span>|<span data-ttu-id="ea930-155">**新しいプラン** グループの作成がオフになっていること、および既存のグループへのプランの追加を提供することを説明します。</span><span class="sxs-lookup"><span data-stu-id="ea930-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="ea930-156">Web およびロードマップのプロジェクト</span><span class="sxs-lookup"><span data-stu-id="ea930-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="ea930-157">[**グループの作成**] メニューグループの作成が制限されていて、既存のグループを使用していることを説明します。</span><span class="sxs-lookup"><span data-stu-id="ea930-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="ea930-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ea930-158">SharePoint</span></span>|<span data-ttu-id="ea930-159">グループに接続されていないチームサイトを作成することはできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="ea930-160">Stream</span><span class="sxs-lookup"><span data-stu-id="ea930-160">Stream</span></span>|<span data-ttu-id="ea930-161">[**作成] メニュー** の下に [**グループ**] オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="ea930-162">Teams</span><span class="sxs-lookup"><span data-stu-id="ea930-162">Teams</span></span>|<span data-ttu-id="ea930-163">ユーザーが新しいグループを使用してチームを作成することはできませんが、既存のグループを利用するチームを作成することはできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="ea930-164">[**チームの作成**] ボタンは、**グループからのチームの作成** に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="ea930-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="ea930-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="ea930-165">Yammer</span></span>|<span data-ttu-id="ea930-166">[**グループの作成**] オプションは、メイングループ/コミュニティナビゲーションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="ea930-167">サービスとグループの相互作用</span><span class="sxs-lookup"><span data-stu-id="ea930-167">Services interactions with groups</span></span>

<span data-ttu-id="ea930-168">さまざまな種類のグループ、それらの作成および管理方法、およびガバナンスに関する推奨事項については、Microsoft 365 ポスターのグループを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea930-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="ea930-169">[![グループ インフォグラフィックのサムネイル](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="ea930-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="ea930-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="ea930-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="ea930-171">次の表は、Microsoft 365 グループのさまざまなサービスとの相互作用の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea930-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="ea930-172">製品</span><span class="sxs-lookup"><span data-stu-id="ea930-172">Product</span></span>|<span data-ttu-id="ea930-173">機能</span><span class="sxs-lookup"><span data-stu-id="ea930-173">Features</span></span>|<span data-ttu-id="ea930-174">サービス</span><span class="sxs-lookup"><span data-stu-id="ea930-174">Does the service</span></span><br><span data-ttu-id="ea930-175">グループを使用しない場合</span><span class="sxs-lookup"><span data-stu-id="ea930-175">exist without a group?</span></span>|<span data-ttu-id="ea930-176">サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-176">Can the service</span></span><br><span data-ttu-id="ea930-177">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="ea930-177">create a group?</span></span>|<span data-ttu-id="ea930-178">を削除します。</span><span class="sxs-lookup"><span data-stu-id="ea930-178">Does deleting the</span></span><br><span data-ttu-id="ea930-179">インスタンスはグループを削除しますか?</span><span class="sxs-lookup"><span data-stu-id="ea930-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="ea930-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ea930-180">Azure AD</span></span>|<span data-ttu-id="ea930-181">メンバーシップ、グループ制御、ゲスト</span><span class="sxs-lookup"><span data-stu-id="ea930-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="ea930-182">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-182">Yes</span></span>|<span data-ttu-id="ea930-183">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-183">Yes</span></span>|<span data-ttu-id="ea930-184">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-184">Yes</span></span>|
|<span data-ttu-id="ea930-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="ea930-185">Exchange</span></span>|<span data-ttu-id="ea930-186">予定表、メールボックス</span><span class="sxs-lookup"><span data-stu-id="ea930-186">Calendar, mailbox</span></span>|<span data-ttu-id="ea930-187">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-187">Yes</span></span>|<span data-ttu-id="ea930-188">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-188">Yes</span></span>|<span data-ttu-id="ea930-189">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-189">Yes</span></span>|
|<span data-ttu-id="ea930-190">フォーム</span><span class="sxs-lookup"><span data-stu-id="ea930-190">Forms</span></span>|<span data-ttu-id="ea930-191">フォーム</span><span class="sxs-lookup"><span data-stu-id="ea930-191">Form</span></span>|<span data-ttu-id="ea930-192">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-192">Yes</span></span>|<span data-ttu-id="ea930-193">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-193">No</span></span>|<span data-ttu-id="ea930-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-194">No</span></span>|
|<span data-ttu-id="ea930-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="ea930-195">OneNote</span></span>|<span data-ttu-id="ea930-196">ノートブック</span><span class="sxs-lookup"><span data-stu-id="ea930-196">Notebook</span></span>|<span data-ttu-id="ea930-197">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-197">Yes</span></span>|<span data-ttu-id="ea930-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-198">No</span></span>|<span data-ttu-id="ea930-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-199">No</span></span>|
|<span data-ttu-id="ea930-200">Planner</span><span class="sxs-lookup"><span data-stu-id="ea930-200">Planner</span></span>|<span data-ttu-id="ea930-201">タスクボード</span><span class="sxs-lookup"><span data-stu-id="ea930-201">Task board</span></span>|<span data-ttu-id="ea930-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-202">No</span></span>|<span data-ttu-id="ea930-203">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-203">Yes</span></span>|<span data-ttu-id="ea930-204">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-204">Yes</span></span>|
|<span data-ttu-id="ea930-205">Power Apps アプリ</span><span class="sxs-lookup"><span data-stu-id="ea930-205">Power Apps app</span></span>|<span data-ttu-id="ea930-206">アプリ</span><span class="sxs-lookup"><span data-stu-id="ea930-206">App</span></span>|<span data-ttu-id="ea930-207">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-207">Yes</span></span>|<span data-ttu-id="ea930-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-208">No</span></span>|<span data-ttu-id="ea930-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-209">No</span></span>|
|<span data-ttu-id="ea930-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="ea930-210">Power Automate</span></span>|<span data-ttu-id="ea930-211">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="ea930-211">Workflow</span></span>|<span data-ttu-id="ea930-212">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-212">Yes</span></span>|<span data-ttu-id="ea930-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-213">No</span></span>|<span data-ttu-id="ea930-214">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-214">No</span></span>|
|<span data-ttu-id="ea930-215">Power BI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="ea930-215">Power BI (classic)</span></span>|<span data-ttu-id="ea930-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="ea930-216">Workspace</span></span>|<span data-ttu-id="ea930-217">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-217">No</span></span>|<span data-ttu-id="ea930-218">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-218">Yes</span></span>|<span data-ttu-id="ea930-219">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-219">Yes</span></span>|
|<span data-ttu-id="ea930-220">Power BI (新機能)</span><span class="sxs-lookup"><span data-stu-id="ea930-220">Power BI (new)</span></span>|<span data-ttu-id="ea930-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="ea930-221">Workspace</span></span>|<span data-ttu-id="ea930-222">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-222">Yes</span></span>|<span data-ttu-id="ea930-223">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-223">No</span></span>|<span data-ttu-id="ea930-224">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-224">Yes</span></span>|
|<span data-ttu-id="ea930-225">Web 用 Project</span><span class="sxs-lookup"><span data-stu-id="ea930-225">Project for the web</span></span>|<span data-ttu-id="ea930-226">Project plan</span><span class="sxs-lookup"><span data-stu-id="ea930-226">Project plan</span></span>|<span data-ttu-id="ea930-227">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-227">Yes</span></span>|<span data-ttu-id="ea930-228">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-228">Yes</span></span>|<span data-ttu-id="ea930-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-229">No</span></span>|
|<span data-ttu-id="ea930-230">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="ea930-230">Roadmap</span></span>|<span data-ttu-id="ea930-231">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="ea930-231">Roadmap</span></span>|<span data-ttu-id="ea930-232">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-232">Yes</span></span>|<span data-ttu-id="ea930-233">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-233">Yes</span></span>|<span data-ttu-id="ea930-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-234">No</span></span>|
|<span data-ttu-id="ea930-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ea930-235">SharePoint</span></span>|<span data-ttu-id="ea930-236">Site</span><span class="sxs-lookup"><span data-stu-id="ea930-236">Site</span></span>|<span data-ttu-id="ea930-237">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-237">Yes</span></span>|<span data-ttu-id="ea930-238">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-238">Yes</span></span>|<span data-ttu-id="ea930-239">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-239">Yes</span></span>|
|<span data-ttu-id="ea930-240">Stream</span><span class="sxs-lookup"><span data-stu-id="ea930-240">Stream</span></span>|<span data-ttu-id="ea930-241">チャネル、ビデオ</span><span class="sxs-lookup"><span data-stu-id="ea930-241">Channel, video</span></span>|<span data-ttu-id="ea930-242">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-242">Yes</span></span>|<span data-ttu-id="ea930-243">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-243">Yes</span></span>|<span data-ttu-id="ea930-244">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-244">Yes</span></span>|
|<span data-ttu-id="ea930-245">Teams</span><span class="sxs-lookup"><span data-stu-id="ea930-245">Teams</span></span>|<span data-ttu-id="ea930-246">チーム</span><span class="sxs-lookup"><span data-stu-id="ea930-246">Team</span></span>|<span data-ttu-id="ea930-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea930-247">No</span></span>|<span data-ttu-id="ea930-248">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-248">Yes</span></span>|<span data-ttu-id="ea930-249">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-249">Yes</span></span>|
|<span data-ttu-id="ea930-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="ea930-250">Yammer</span></span>|<span data-ttu-id="ea930-251">Group</span><span class="sxs-lookup"><span data-stu-id="ea930-251">Group</span></span>|<span data-ttu-id="ea930-252">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-252">Yes</span></span>|<span data-ttu-id="ea930-253">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-253">Yes</span></span>|<span data-ttu-id="ea930-254">はい</span><span class="sxs-lookup"><span data-stu-id="ea930-254">Yes</span></span>|

<span data-ttu-id="ea930-255">上記の表は、Microsoft 365 サービスとのグループの相互作用の概要を示していますが、いくつかの微妙で複雑で理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="ea930-256">次のセクションでは、特定のワークロードとグループとの相互作用について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ea930-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="ea930-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ea930-257">Azure AD</span></span>

<span data-ttu-id="ea930-258">Azure AD は、Microsoft 365 全体で基盤となる id 管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea930-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="ea930-259">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-260">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="ea930-260">Group membership</span></span>
- <span data-ttu-id="ea930-261">名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="ea930-261">Naming policy</span></span>
- <span data-ttu-id="ea930-262">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="ea930-262">Expiration policy</span></span>
- <span data-ttu-id="ea930-263">者</span><span class="sxs-lookup"><span data-stu-id="ea930-263">Guests</span></span>
- <span data-ttu-id="ea930-264">グループの作成の制限</span><span class="sxs-lookup"><span data-stu-id="ea930-264">Restriction of Group creation</span></span>

<span data-ttu-id="ea930-265">**Azure AD でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="ea930-266">はい。 Microsoft 365 グループは、管理 web ポータル、PowerShell、または Graph API を使用して Azure AD から作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="ea930-267">**Azure AD はグループを使用せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="ea930-268">はい。 Azure AD は、Microsoft 365 グループと関係のない膨大な数のサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea930-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="ea930-269">各 Microsoft 365 グループは、Azure AD のオブジェクトとして表されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="ea930-270">**グループごとに Azure AD の複数のインスタンスが存在することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="ea930-271">いいえ。 Azure AD のインスタンスは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="ea930-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="ea930-272">**Azure AD は複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="ea930-273">はい。これは、Azure AD がグループメンバーシップサービスを提供する基盤となるプラットフォームであるためです。</span><span class="sxs-lookup"><span data-stu-id="ea930-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="ea930-274">**Azure AD とグループの変更を関連付けできますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="ea930-275">いいえ。 Azure AD は、グループが存在する基礎となるプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ea930-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="ea930-276">**インスタンスを削除してグループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="ea930-277">Azure AD でグループを削除すると、関連するグループ関連のサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="ea930-278">Teams</span><span class="sxs-lookup"><span data-stu-id="ea930-278">Teams</span></span>

<span data-ttu-id="ea930-279">Teams は、さまざまな Microsoft やサードパーティのサービスと対話するための単一のインターフェイスを提供することによって、共同作業を強化することを目的としたチャット中心のワークスペースです。</span><span class="sxs-lookup"><span data-stu-id="ea930-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="ea930-280">既定では、チームを作成すると、Microsoft 365 グループに関連付けられているメールボックスと予定表は、Exchange のグローバルアドレス一覧および Outlook の両方から非表示になります。</span><span class="sxs-lookup"><span data-stu-id="ea930-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="ea930-281">ユーザーが同じ Microsoft 365 グループの Outlook と Teams の両方を使用する場合は、管理者が手動で上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="ea930-282">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-283">会話</span><span class="sxs-lookup"><span data-stu-id="ea930-283">Conversations</span></span>
- <span data-ttu-id="ea930-284">チャネル & タブ</span><span class="sxs-lookup"><span data-stu-id="ea930-284">Channels & tabs</span></span>
- <span data-ttu-id="ea930-285">会議</span><span class="sxs-lookup"><span data-stu-id="ea930-285">Meetings</span></span>

<span data-ttu-id="ea930-286">**Teams でグループを作成することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="ea930-287">はい。新しいチームを作成すると、新しい Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="ea930-288">現在のグループが存在しない既存のグループに対してチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="ea930-289">**チームはグループを使用せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="ea930-290">いいえ。グループを使用せずにチームを存在させることはできません。</span><span class="sxs-lookup"><span data-stu-id="ea930-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="ea930-291">**グループごとに複数のチームが存在することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="ea930-292">いいえ。チームとグループの関係は1:1 です。</span><span class="sxs-lookup"><span data-stu-id="ea930-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="ea930-293">**チームを複数のグループに関連付けることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-294">いいえ。チーム自体は1つのグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="ea930-295">**チームとグループの間の関連付けは変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="ea930-296">いいえ。チームは、もともと関連付けられていたグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="ea930-297">**チームを削除することによってグループを削除するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="ea930-298">はい、Microsoft Teams のチームを削除すると、グループ、グループに関連付けられたサービス、およびコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="ea930-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="ea930-299">Exchange</span></span>

<span data-ttu-id="ea930-300">Exchange Online は、メッセージング、予定表、連絡先、および関連付けられた機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea930-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="ea930-301">グループのコンテキストでは、サービスインスタンス全体ではなく、1つのリソースのみが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ea930-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="ea930-302">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-303">メールボックスと予定表</span><span class="sxs-lookup"><span data-stu-id="ea930-303">Mailbox and calendar</span></span>
- <span data-ttu-id="ea930-304">すべてのグループメンバーにメールを送信する機能</span><span class="sxs-lookup"><span data-stu-id="ea930-304">Ability to email all Group members</span></span>
- <span data-ttu-id="ea930-305">電子情報開示のためのチームチャネル会話の保存、Planner コメント</span><span class="sxs-lookup"><span data-stu-id="ea930-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="ea930-306">**Exchange でグループを作成できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="ea930-307">はい。 Exchange Online 管理センターおよび Outlook からグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="ea930-308">また、Exchange の配布リストを Microsoft 365 グループに変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="ea930-309">**Exchange がグループなしで存在するかどうか**</span><span class="sxs-lookup"><span data-stu-id="ea930-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="ea930-310">はい。 Exchange Online には、共有されたメールボックスや予定表など、いくつかのサービスがあります。グループの関連付けはありません。</span><span class="sxs-lookup"><span data-stu-id="ea930-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="ea930-311">**Exchange メールボックスまたはグループごとのカレンダーのインスタンスが複数存在することはできますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="ea930-312">いいえ。グループには、1つの Exchange Online メールボックスと予定表のみを配置できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="ea930-313">**Exchange メールボックスと予定表は、複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-314">いいえ。メールボックスと予定表には、グループと1:1 の関係があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="ea930-315">メールボックスを他のユーザーまたはグループと共有することはできますが、これは何らかの形式のサービス関連付けを確立しません。</span><span class="sxs-lookup"><span data-stu-id="ea930-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="ea930-316">**Exchange メールボックスまたは予定表がグループとの関連付けを変更できるかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="ea930-317">いいえ、メールボックスと予定表を別のグループに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea930-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="ea930-318">ただし、Outlook 内で、またはサードパーティ製ツールを使用して、あるメールボックスから別のメールボックスにコンテンツを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="ea930-319">**メールボックスを削除するグループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="ea930-320">はい。 Exchange のメールボックスを削除すると、グループに関連付けられたサービスとコンテンツも削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="ea930-321">フォーム</span><span class="sxs-lookup"><span data-stu-id="ea930-321">Forms</span></span>

<span data-ttu-id="ea930-322">フォームには、web ベースのアンケートとクイズが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea930-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="ea930-323">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="ea930-324">フォームの所有権</span><span class="sxs-lookup"><span data-stu-id="ea930-324">Ownership of forms</span></span>

<span data-ttu-id="ea930-325">**フォームでグループを作成することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="ea930-326">いいえ、フォームはグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="ea930-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="ea930-327">**フォームはグループ化せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="ea930-328">はい、アンケートとクイズをエンドユーザーのアカウントに直接作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="ea930-329">**グループごとに複数のフォームがあるかどうか**</span><span class="sxs-lookup"><span data-stu-id="ea930-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="ea930-330">はい。グループに関連付けられているフォームが複数存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="ea930-331">**フォームは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-332">いいえ。フォームは1つのグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="ea930-333">**フォームとグループの関連付けを変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="ea930-334">フォームがグループ (内部で直接作成されているか、または個別の所有権を持つ) に関連付けられている場合は、別のグループに移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea930-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="ea930-335">**フォームを削除することによってグループを削除するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="ea930-336">いいえ。フォームインターフェイスからグループを削除することはできません。個別のフォームのみです。</span><span class="sxs-lookup"><span data-stu-id="ea930-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="ea930-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="ea930-337">OneNote</span></span>

<span data-ttu-id="ea930-338">OneNote はデジタルノートブックアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ea930-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="ea930-339">グループによって作成された OneNote ノートブックは、グループに接続されたサービスではなく、関連付けられた SharePoint サイトのファイルです。</span><span class="sxs-lookup"><span data-stu-id="ea930-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="ea930-340">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="ea930-341">共有ノートブック (グループに関連付けられた SharePoint ライブラリに保存)</span><span class="sxs-lookup"><span data-stu-id="ea930-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="ea930-342">**OneNote はグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="ea930-343">いいえ。 OneNote アプリケーションはグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="ea930-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="ea930-344">**OneNote ノートブックはグループを使用せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="ea930-345">はい。 OneDrive または他の共有場所にあるノートブックを直接作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="ea930-346">**グループごとに複数の OneNote ノートブックを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="ea930-347">はい。ノートブックは既定で作成され、他のユーザーを追加できます。ただし、グループに関連付けられたサービスからの OneNote へのリンクは常に既定のノートブックに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea930-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="ea930-348">**OneNote ノートブックは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-349">いいえ。このノートブックは、グループに関連付けられた SharePoint サイトライブラリに格納され、さまざまなインターフェイスからリンクされています。</span><span class="sxs-lookup"><span data-stu-id="ea930-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="ea930-350">ただし、個人と共有する場合と同じ方法で、他のグループと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="ea930-351">**ノートブックとグループの関連付けは変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="ea930-352">いいえ。ノートブック自体はグループに関連付けられており、他のグループに接続されたサービスから直接アクセスすることができますが、コンテンツを OneNote アプリケーション内の別のノートブックに移動できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="ea930-353">**ノートブックを削除すると、グループが削除されますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="ea930-354">ただし、OneNote ノートブックが削除された場合は、一部のグループ関連サービスのリンクが壊れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="ea930-355">Planner</span><span class="sxs-lookup"><span data-stu-id="ea930-355">Planner</span></span>

<span data-ttu-id="ea930-356">Planner は、ライトウェイトグループタスク管理サービスです。</span><span class="sxs-lookup"><span data-stu-id="ea930-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="ea930-357">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="ea930-358">グループタスクを管理するためのボード</span><span class="sxs-lookup"><span data-stu-id="ea930-358">Board for managing group tasks</span></span>

<span data-ttu-id="ea930-359">**プランナーでグループを作成することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="ea930-360">はい。プランを作成すると、新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="ea930-361">**Planner ボードはグループを使用せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="ea930-362">いいえ。プランは、グループに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="ea930-363">**グループごとに複数のプランを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="ea930-364">はい。グループごとに複数のプランが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="ea930-365">**プランは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-366">いいえ。プランでは、アクセスを決定するためにグループメンバーシップだけに依存しています。</span><span class="sxs-lookup"><span data-stu-id="ea930-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="ea930-367">**プランがグループの変更に関連付けられているかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="ea930-368">いいえ。プランをコピーすると、新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="ea930-369">その他のアプリケーションによって作成されたグループは、ユーザーに対して自動的に Planner に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="ea930-370">最初にボードにアクセスするには、Outlook などの別のグループベースのインターフェイスから開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea930-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="ea930-371">**プランを削除することによってグループを削除するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="ea930-372">はい。プランを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="ea930-373">Power アプリ</span><span class="sxs-lookup"><span data-stu-id="ea930-373">Power Apps</span></span>

<span data-ttu-id="ea930-374">Power Apps には、コードを使用せずにアプリ開発用のキャンバスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea930-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="ea930-375">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-376">アプリをグループと共有して、実行および変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="ea930-377">**電源アプリでグループを作成できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="ea930-378">いいえ。 Power Apps は Microsoft 365 グループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="ea930-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="ea930-379">**グループを使用せずに Power Apps が存在するかどうか**</span><span class="sxs-lookup"><span data-stu-id="ea930-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="ea930-380">はい。アプリは、共有または公開するまで、Power Apps 内に作成し、クリエーターアカウント内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="ea930-381">**グループごとに複数のアプリを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="ea930-382">はい。複数のアプリをグループと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="ea930-383">**アプリは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-384">はい、アプリを複数のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="ea930-385">**アプリとグループの関連付けを変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="ea930-386">はい。電源アプリと Microsoft 365 グループの間の関連付けが共有のみであるため、アプリは作成者と共に存在します。</span><span class="sxs-lookup"><span data-stu-id="ea930-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea930-387">[アプリを共有できるようにするには、グループのセキュリティが有効になっている必要があり](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)ます。</span><span class="sxs-lookup"><span data-stu-id="ea930-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="ea930-388">**アプリを削除すると、グループが削除されますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="ea930-389">いいえ。アプリは、そのグループと共有されている以外のグループに接続されていません。</span><span class="sxs-lookup"><span data-stu-id="ea930-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="ea930-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="ea930-390">Power Automate</span></span>

<span data-ttu-id="ea930-391">パワー・オートメーション (旧称 Microsoft Flow) は、ワークフローと自動化サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea930-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="ea930-392">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="ea930-393">ワークフローは、グループと共有して、実行および変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="ea930-394">**電源を自動化してグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="ea930-395">いいえ。 Microsoft 365 グループは、そのグループに関連付けられているコンテキストでは作成できません。</span><span class="sxs-lookup"><span data-stu-id="ea930-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="ea930-396">ただし、Azure AD セキュリティグループの作成、Microsoft 365 グループのメンバーシップの更新など、さまざまな操作を実行するフローを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="ea930-397">**フローがグループ化せずに存在するかどうか**</span><span class="sxs-lookup"><span data-stu-id="ea930-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="ea930-398">はい。フローは、電力の自動生成中に作成でき、共有または公開するまでクリエーターアカウント内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="ea930-399">**グループごとに複数のフローがありますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="ea930-400">はい。グループと複数のフローを共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="ea930-401">**フローは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-402">はい。複数のグループとフローを共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="ea930-403">**グループの変更に対してフローの関連付けを行うことはできますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="ea930-404">はい。電源をオンにした場合と Microsoft 365 グループが共有されている場合の関連付けとして、フローは作成者にも存在します。</span><span class="sxs-lookup"><span data-stu-id="ea930-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="ea930-405">**フローを削除してグループを削除するか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="ea930-406">いいえ。電源アプリと同様に、フローは共有ではないグループに接続されていません。</span><span class="sxs-lookup"><span data-stu-id="ea930-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="ea930-407">Power BI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="ea930-407">Power BI (classic)</span></span>

<span data-ttu-id="ea930-408">Power BI は、対話的なデータ駆動型のダッシュボードとレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea930-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="ea930-409">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="ea930-410">データの報告</span><span class="sxs-lookup"><span data-stu-id="ea930-410">Data reporting</span></span>

<span data-ttu-id="ea930-411">**Power BI がグループを作成できるかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="ea930-412">はい。クラシックワークスペースを作成すると、Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="ea930-413">**Power BI クラシックワークスペースは、グループ化されていませんか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="ea930-414">いいえ。 [POWER BI のクラシックワークスペースは、グループに関連付けられている必要があり](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)ます。</span><span class="sxs-lookup"><span data-stu-id="ea930-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="ea930-415">**グループごとに複数の Power BI ワークスペースを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="ea930-416">いいえ。クラシックワークスペースとグループの関係は1:1 です。</span><span class="sxs-lookup"><span data-stu-id="ea930-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="ea930-417">**ワークスペースは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-418">技術的には、クラシックワークスペースはグループと共に作成されますが、ユーザーおよびセキュリティグループを使用して、グループの外部でコンテンツを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="ea930-419">**ワークスペースのグループとの関連付けを変更することはできますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="ea930-420">いいえ。クラシックワークスペース自体はグループに関連付けられますが、Power BI インターフェイス内のワークスペース間で、またはコンテンツをローカルでエクスポートすることで、コンテンツを別のワークスペースに移動できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="ea930-421">**ワークスペースを削除するグループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="ea930-422">はい。 Power BI でワークスペースを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="ea930-423">Power BI (新機能)</span><span class="sxs-lookup"><span data-stu-id="ea930-423">Power BI (new)</span></span>

<span data-ttu-id="ea930-424">Power BI は、対話的なデータ駆動型のダッシュボードとレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea930-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="ea930-425">Power BI で新しいワークスペースを作成しても、Microsoft 365 グループは作成されませんが、その他の方法でグループを作成すると、Power BI に新しい (非クラシック) ワークスペースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="ea930-426">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="ea930-427">データの報告</span><span class="sxs-lookup"><span data-stu-id="ea930-427">Data reporting</span></span>

<span data-ttu-id="ea930-428">**Power BI がグループを作成できるかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="ea930-429">いいえ。新しい Power BI インターフェイスから Microsoft 365 グループを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea930-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="ea930-430">**新しい Power BI ワークスペースはグループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="ea930-431">はい。 Microsoft 365 グループに関連付けられていないレポートとワークスペースを Power BI で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="ea930-432">**グループごとに複数のワークスペースを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="ea930-433">はい、 [POWER BI によって作成された複数のワークスペースを1つのグループと共有でき](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)ます。</span><span class="sxs-lookup"><span data-stu-id="ea930-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="ea930-434">**ワークスペースは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-435">いいえ。 Power BI によって作成されたワークスペースは、1つのグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="ea930-436">**ワークスペースのグループへの関連付けは変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="ea930-437">さあ何とも言えません。</span><span class="sxs-lookup"><span data-stu-id="ea930-437">Yes and no.</span></span> <span data-ttu-id="ea930-438">Power BI によって作成されたワークスペースは、一度に1つのグループにのみ関連付けることができますが、いつでも関連付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="ea930-439">グループによって Power BI に作成されたワークスペースは、そのグループに永続的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ea930-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="ea930-440">**ワークスペースを削除するグループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="ea930-441">はい。 Power BI でワークスペースを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="ea930-442">Web 用 Project</span><span class="sxs-lookup"><span data-stu-id="ea930-442">Project for the web</span></span>

<span data-ttu-id="ea930-443">Project for web には、プロジェクト計画、ガントチャート、およびロードマップを作成する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea930-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="ea930-444">グループに提供される主な機能。</span><span class="sxs-lookup"><span data-stu-id="ea930-444">Key features provided to groups.</span></span>

- <span data-ttu-id="ea930-445">プロジェクト計画</span><span class="sxs-lookup"><span data-stu-id="ea930-445">Project plans</span></span>

<span data-ttu-id="ea930-446">**プロジェクトを web で使用できるグループを作成する**</span><span class="sxs-lookup"><span data-stu-id="ea930-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="ea930-447">はい。 web 用の Project から直接新しい Microsoft 365 グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="ea930-448">**プロジェクトがグループ化せずに存在するかどうか**</span><span class="sxs-lookup"><span data-stu-id="ea930-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="ea930-449">はい。 Microsoft 365 グループに関連付けずにプロジェクトを存在させることができます。ただし、タスクの割り当てにはグループの関連付けが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea930-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="ea930-450">**グループごとに複数のプロジェクトを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="ea930-451">はい。1つのグループに複数のプロジェクトを接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="ea930-452">**プロジェクトを複数のグループに関連付けることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-453">いいえ。プロジェクトは1つのグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="ea930-454">**プロジェクトとグループの間の関連付けは変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="ea930-455">いいえ、グループとの関連付けが確立されると、変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ea930-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="ea930-456">**プロジェクトを削除してグループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="ea930-457">いいえ。 web のプロジェクトのプロジェクトを削除しても、グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="ea930-458">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="ea930-458">Roadmap</span></span>

<span data-ttu-id="ea930-459">ロードマップでは、project を使用してプロジェクトロードマップを web および Project Online で作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="ea930-460">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-461">プロジェクトロードマップ</span><span class="sxs-lookup"><span data-stu-id="ea930-461">Project roadmaps</span></span>

<span data-ttu-id="ea930-462">**ロードマップはグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="ea930-463">はい。新しい Microsoft 365 グループをロードマップから直接作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="ea930-464">**ロードマップはグループ化されていませんか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="ea930-465">はい、Microsoft 365 グループに関連付けられていない状態でロードマップを使用できますが、ロードマップを共有するには、グループの関連付けが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea930-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="ea930-466">**グループごとに複数のロードマップを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="ea930-467">はい。複数のロードマップを1つのグループに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="ea930-468">**ロードマップは複数のグループに関連付けることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-469">いいえ、ロードマップは1つのグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="ea930-470">**ロードマップがグループの変更と関連付けられているかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="ea930-471">いいえ、グループとの関連付けが確立されると、変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ea930-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="ea930-472">**ロードマップを削除するグループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="ea930-473">いいえ。ロードマップを削除してもグループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="ea930-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ea930-474">SharePoint</span></span>

<span data-ttu-id="ea930-475">SharePoint は、さまざまな Microsoft 365 サービスのストレージサービスを提供する web ベースのコンテンツ管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ea930-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="ea930-476">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-477">ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ea930-477">Document library</span></span>
- <span data-ttu-id="ea930-478">OneNote ノートブックのストレージ用のライブラリ</span><span class="sxs-lookup"><span data-stu-id="ea930-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="ea930-479">Teams wiki ファイルの保存</span><span class="sxs-lookup"><span data-stu-id="ea930-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="ea930-480">**SharePoint でグループを作成できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="ea930-481">はい。 SharePoint でチームサイトを作成すると、既定で Microsoft 365 グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="ea930-482">グループと、必要に応じて、既存のサイトのチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="ea930-483">**SharePoint サイトはグループを使用せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="ea930-484">はい。 SharePoint には、グループに関連付けられていないいくつかのサービスと、コミュニケーションサイトやハブサイトなどのサイトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea930-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="ea930-485">**グループごとに複数のサイトが存在することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="ea930-486">いいえ。グループごとに1つのサイトしか存在できません。</span><span class="sxs-lookup"><span data-stu-id="ea930-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="ea930-487">Teams のプライベートチャネルは、グループに接続されていない追加サイトを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea930-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="ea930-488">**サイトを複数のグループに関連付けることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-489">技術的にはありませんが、グループを使用してサイトを作成すると、そのコンテンツを他のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="ea930-490">**サイトとグループの関連付けを変更することはできますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="ea930-491">いいえ。サイト自体はグループに関連付けられていますが、コンテンツをローカルにエクスポートするか、またはサードパーティ製ツールを使用してサイト間で移動することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="ea930-492">**サイトを削除することによってグループを削除するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="ea930-493">はい。 SharePoint でサイトを削除すると、グループとグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="ea930-494">Stream</span><span class="sxs-lookup"><span data-stu-id="ea930-494">Stream</span></span>

<span data-ttu-id="ea930-495">Microsoft Stream は、ビデオをホスティングおよび共有するプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ea930-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="ea930-496">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-497">ビデオストレージ</span><span class="sxs-lookup"><span data-stu-id="ea930-497">Video storage</span></span>
- <span data-ttu-id="ea930-498">Teams 会議のレコーディング</span><span class="sxs-lookup"><span data-stu-id="ea930-498">Teams meeting recording</span></span>
- <span data-ttu-id="ea930-499">ビデオチャネル</span><span class="sxs-lookup"><span data-stu-id="ea930-499">Video channels</span></span>

<span data-ttu-id="ea930-500">**グループ作成をストリーミングできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="ea930-501">はい。新しい Microsoft 365 グループを Stream から直接作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="ea930-502">**Stream はグループを使用せずに存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="ea930-503">はい、ビデオチャネルとビデオは、グループに関連付けられていないストリームに存在することができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="ea930-504">**グループごとに複数のビデオやチャネルを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="ea930-505">はい、各グループに複数のビデオやチャネルを配置できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="ea930-506">**ビデオやチャネルを複数のグループに関連付けることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="ea930-507">はい。グループを使用してビデオやチャネルを作成すると、他のグループと共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea930-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="ea930-508">**グループとの関連付けを変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="ea930-509">はいStream 内のビデオは、元のアップローダーまたは会議レコーダーが所有しているため、任意のグループに関連付けることができます。ただし、ビデオチャネルは、もともと作成されたグループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="ea930-510">**ビデオまたはチャネルを削除すると、グループが削除されますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="ea930-511">いいえ。ビデオまたはチャネルを削除してもグループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ea930-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="ea930-512">ただし、Stream のグループ自体を削除すると、実際のビデオ以外のグループに関連付けられたサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="ea930-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="ea930-513">Yammer</span></span>

<span data-ttu-id="ea930-514">Yammer は、組織間および組織間でのコミュニティの参加を促進するために設計されたエンタープライズソーシャルプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ea930-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="ea930-515">Yammer のコミュニティ (旧称 "グループ") を作成するとメールボックスが作成されますが、現在は使用されていません。</span><span class="sxs-lookup"><span data-stu-id="ea930-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="ea930-516">Yammer に関連付けられている Microsoft 365 グループは、Microsoft Teams のチームと一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea930-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="ea930-517">**グループに提供される主な機能**</span><span class="sxs-lookup"><span data-stu-id="ea930-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="ea930-518">会話領域</span><span class="sxs-lookup"><span data-stu-id="ea930-518">Conversation area</span></span>

<span data-ttu-id="ea930-519">**Yammer で Microsoft 365 グループを作成することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="ea930-520">はい、Yammer で新しいグループを作成すると、新しい Microsoft 365 グループが作成されます (プラットフォームが接続されていて、ユーザーがグループを作成できます)。</span><span class="sxs-lookup"><span data-stu-id="ea930-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="ea930-521">Microsoft 365 グループが関連付けられている Yammer グループを、Yammer 自体以外のインターフェイスまたはサービスで作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea930-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="ea930-522">**Yammer グループは、Microsoft 365 グループなしで存在しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="ea930-523">はい。 Microsoft 365 グループを使用せずに Yammer グループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea930-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="ea930-524">Yammer プラットフォームが Microsoft 365 グループに接続されていない場合や、ユーザーが Microsoft 365 グループを作成できない場合は、Microsoft 365 グループの関連付けなしで Yammer グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="ea930-525">**Microsoft 365 グループあたり複数の Yammer グループが存在することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="ea930-526">いいえ、Yammer グループと Microsoft 365 グループの間の関係は1:1 です。</span><span class="sxs-lookup"><span data-stu-id="ea930-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="ea930-527">**Yammer グループを複数の Microsoft 365 グループに関連付けることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="ea930-528">いいえ。 Yammer グループは、1つの Microsoft 365 グループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="ea930-529">他の Yammer グループとの間で投稿を共有したり移動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="ea930-530">**Yammer グループと Microsoft 365 グループの関連付けは変更できますか。**</span><span class="sxs-lookup"><span data-stu-id="ea930-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="ea930-531">いいえ。 Yammer グループは、もともと関連付けられていた Microsoft 365 グループにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea930-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="ea930-532">**Yammer グループを削除するには、Microsoft 365 グループを削除しますか?**</span><span class="sxs-lookup"><span data-stu-id="ea930-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="ea930-533">はい、Yammer のグループを削除すると、関連する Microsoft グループおよびグループ関連のサービスとコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea930-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea930-534">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea930-534">Related topics</span></span>

[<span data-ttu-id="ea930-535">コラボレーションガバナンスの計画のステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="ea930-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="ea930-536">コラボレーションのガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="ea930-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

