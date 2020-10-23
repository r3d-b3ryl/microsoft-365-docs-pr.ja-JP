---
title: グループ、teams、Yammer のライフサイクルの終了オプション
ms.reviewer: mmclean
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
description: グループ、teams、Yammer のライフサイクルの終了オプション。
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681712"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a><span data-ttu-id="c68f9-103">グループ、teams、Yammer のライフサイクルの終了オプション</span><span class="sxs-lookup"><span data-stu-id="c68f9-103">End of lifecycle options for groups, teams, and Yammer</span></span>

<span data-ttu-id="c68f9-104">Microsoft 365 グループと Microsoft Teams は、接続されたさまざまなサービスと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-104">Microsoft 365 Groups and Microsoft Teams work with a variety of connected services.</span></span> <span data-ttu-id="c68f9-105">グループまたはチームを削除すると、接続されているサービスの情報の大部分も削除されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-105">When a group or team is deleted, most of the information in the connected services is also deleted.</span></span> <span data-ttu-id="c68f9-106">この記事では、削除する前にグループまたはチームから情報を保持するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-106">This article describes options for retaining information by moving it out of the group or team prior to deletion.</span></span>

<span data-ttu-id="c68f9-107">不要になったグループまたはチームのための一般的な手法として、ファイルをチーム外に移動し、リポジトリまたはアーカイブとして機能する SharePoint ドキュメントライブラリなどの別の場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-107">A common practice for groups or teams that are no longer required is to move the files out of the team and store them in another location such as a SharePoint document library acting as a repository or archive.</span></span> <span data-ttu-id="c68f9-108">このプラクティスは、ファイルやフォルダー内に情報が格納され、電子メール経由で通信が行われる従来のスタイルの作業に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c68f9-108">This practice is based on a legacy style of working where information is stored within files and folders, and communications are conducted via email.</span></span>

<span data-ttu-id="c68f9-109">次の表は、グループと teams に関連付けられているサービスと、各グループに含まれるコンテンツのキーの種類の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c68f9-109">The following table outlines the services associated with groups and teams and key types of content found in each of them:</span></span>

|<span data-ttu-id="c68f9-110">サービス</span><span class="sxs-lookup"><span data-stu-id="c68f9-110">Service</span></span>|<span data-ttu-id="c68f9-111">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="c68f9-111">Types of content</span></span>|
|:------|:---------------|
|<span data-ttu-id="c68f9-112">Teams</span><span class="sxs-lookup"><span data-stu-id="c68f9-112">Teams</span></span>|<span data-ttu-id="c68f9-113">チャネル会話、チャネル内のファイル</span><span class="sxs-lookup"><span data-stu-id="c68f9-113">Channel conversations, files in channels</span></span>|
|<span data-ttu-id="c68f9-114">フォーム</span><span class="sxs-lookup"><span data-stu-id="c68f9-114">Forms</span></span>|<span data-ttu-id="c68f9-115">アンケートの構造と結果</span><span class="sxs-lookup"><span data-stu-id="c68f9-115">Survey structure and results</span></span>|
|<span data-ttu-id="c68f9-116">OneNote</span><span class="sxs-lookup"><span data-stu-id="c68f9-116">OneNote</span></span>|<span data-ttu-id="c68f9-117">ノートブック</span><span class="sxs-lookup"><span data-stu-id="c68f9-117">Notebook</span></span>|
|<span data-ttu-id="c68f9-118">Outlook</span><span class="sxs-lookup"><span data-stu-id="c68f9-118">Outlook</span></span>|<span data-ttu-id="c68f9-119">メールと予定表</span><span class="sxs-lookup"><span data-stu-id="c68f9-119">Mail and calendar</span></span>|
|<span data-ttu-id="c68f9-120">Planner</span><span class="sxs-lookup"><span data-stu-id="c68f9-120">Planner</span></span>|<span data-ttu-id="c68f9-121">プロジェクトの進捗状況およびタスク情報</span><span class="sxs-lookup"><span data-stu-id="c68f9-121">Project status and task information</span></span>|
|<span data-ttu-id="c68f9-122">Power Automate</span><span class="sxs-lookup"><span data-stu-id="c68f9-122">Power Automate</span></span>|<span data-ttu-id="c68f9-123">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c68f9-123">Workflows</span></span>|
|<span data-ttu-id="c68f9-124">Power BI</span><span class="sxs-lookup"><span data-stu-id="c68f9-124">Power BI</span></span>|<span data-ttu-id="c68f9-125">データ、レポート、およびダッシュボード</span><span class="sxs-lookup"><span data-stu-id="c68f9-125">Data, reports, and dashboards</span></span>|
|<span data-ttu-id="c68f9-126">Web 上の Project</span><span class="sxs-lookup"><span data-stu-id="c68f9-126">Project on the web</span></span>|<span data-ttu-id="c68f9-127">プロジェクト計画</span><span class="sxs-lookup"><span data-stu-id="c68f9-127">Project plans</span></span>|
|<span data-ttu-id="c68f9-128">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="c68f9-128">Roadmap</span></span>|<span data-ttu-id="c68f9-129">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="c68f9-129">Roadmaps</span></span>|
|<span data-ttu-id="c68f9-130">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c68f9-130">SharePoint</span></span>|<span data-ttu-id="c68f9-131">ファイル、リスト、Teams チャネル wiki データ</span><span class="sxs-lookup"><span data-stu-id="c68f9-131">Files, lists, Teams channel wiki data</span></span>|
|<span data-ttu-id="c68f9-132">Stream</span><span class="sxs-lookup"><span data-stu-id="c68f9-132">Stream</span></span>|<span data-ttu-id="c68f9-133">動画</span><span class="sxs-lookup"><span data-stu-id="c68f9-133">Videos</span></span>|
|<span data-ttu-id="c68f9-134">Yammer</span><span class="sxs-lookup"><span data-stu-id="c68f9-134">Yammer</span></span>|<span data-ttu-id="c68f9-135">会話</span><span class="sxs-lookup"><span data-stu-id="c68f9-135">Conversations</span></span>|

<span data-ttu-id="c68f9-136">グループまたはチームを削除すると、関連付けられているリソースのほとんども削除されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-136">When deleting a group or team, most of the associated resources are also deleted.</span></span> <span data-ttu-id="c68f9-137">このような一部の例外には、ストリームのビデオが含まれています。これらは、電力の自動化でフローした場合と同様に、アップロードまたは録音したユーザーによって所有されることもあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-137">Some of the exceptions to this include videos in Stream – these remain and are still owned by the person who uploaded/recorded them, as do flows in Power Automate.</span></span> <span data-ttu-id="c68f9-138">Web 上のプロジェクトおよびロードマップデータは、CD に残り、個別に復元することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-138">Project and roadmap data in Project on the web remains in the CDS and can be restored separately.</span></span>

<span data-ttu-id="c68f9-139">グループと teams は、30日間、回復可能な削除の状態が維持され、いつでも復元できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-139">Groups and teams remain in a soft-delete state for 30 days and can be restored at any time.</span></span> <span data-ttu-id="c68f9-140">ただし、30日間の期間が経過すると、サービスやコンテンツなどの関連付けられたリソースは、Microsoft 365 環境から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-140">However, after the 30 days they, and any associated resources such as services and content, are completely purged from the Microsoft 365 environment.</span></span> <span data-ttu-id="c68f9-141">アイテム保持ポリシーによって保護されたコンテンツは、電子情報開示検索によって引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-141">Any content protected by a retention policy remains available through eDiscovery searches.</span></span>

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a><span data-ttu-id="c68f9-142">グループに接続されたサービスの有効期間の終了に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c68f9-142">End of life cycle considerations for group-connected services</span></span>

<span data-ttu-id="c68f9-143">グループまたはチームを削除する際に、チームとグループの所有者と IT 管理者が考慮する必要がある3つの主要な領域があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-143">There are three key areas that team and group owners and IT administrators need to consider when deleting a group or team.</span></span>

<span data-ttu-id="c68f9-144">**Content**</span><span class="sxs-lookup"><span data-stu-id="c68f9-144">**Content**</span></span>

<span data-ttu-id="c68f9-145">チームが機能しなくなった、または存在しなくなった後に、コンテンツを保持する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="c68f9-145">Does the content need to be retained after the team is no longer functional or in existence?</span></span> <span data-ttu-id="c68f9-146">Microsoft 365 の保持機能に依存しているかどうか、または、保存期間を提供しないアプリやサービスのコンテンツの一部ですか。</span><span class="sxs-lookup"><span data-stu-id="c68f9-146">Is it sufficient to rely on retention capabilities of Microsoft 365, or is some of the content in apps and services that do not offer retention?</span></span> <span data-ttu-id="c68f9-147">コンテンツは、レコード管理の目的で、アーカイブの目的で、または将来の使用と参照の目的のために保持する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="c68f9-147">Does the content need to be retained for record management purposes, for archival purposes, or for future use and reference purposes?</span></span>

<span data-ttu-id="c68f9-148">データ損失の可能性を回避するために、チームをアーカイブまたは削除する前に、これらの質問をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-148">These questions must be asked before any team is archived or deleted, to avoid any potential data loss.</span></span>

<span data-ttu-id="c68f9-149">**サービス**</span><span class="sxs-lookup"><span data-stu-id="c68f9-149">**Services**</span></span>

<span data-ttu-id="c68f9-150">さまざまなアプリやサービスにわたるコンテンツの上に、現在作業中のフォームにとどまる必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="c68f9-150">On top of the content across various apps and services, do they need to stay in their current working form?</span></span> <span data-ttu-id="c68f9-151">たとえば、Power BI レポートに引き続きアクセスできるようにする必要があるかどうかは、視覚的な概要ビューでフォームの結果を表示できるようにする必要があるか、または任意の場所にリンクされているか、または埋め込まれている SharePoint のリストですか。</span><span class="sxs-lookup"><span data-stu-id="c68f9-151">For example, does the Power BI report need to continue to be accessible, do the Form results need to be available in the visual summary view, are the lists in SharePoint linked to or embedded anywhere?</span></span>

<span data-ttu-id="c68f9-152">コンテンツをエクスポートするだけでは不十分な場合があるので、コンテンツの考慮事項と同様に、基になるグループが削除される前にこれらの質問をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-152">Similar to the content considerations, these questions must be asked before the underlying group is deleted as simply exporting the content may not be sufficient.</span></span>

<span data-ttu-id="c68f9-153">**者**</span><span class="sxs-lookup"><span data-stu-id="c68f9-153">**Guests**</span></span>

<span data-ttu-id="c68f9-154">ゲストがチームに招待されると、ワークフローはホスト組織の Azure Active Directory に id を作成してからチームに追加します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-154">When guests are invited to a team, the workflow creates their identity in the host organization’s Azure Active Directory before adding them to the team.</span></span> <span data-ttu-id="c68f9-155">チームを削除すると、ゲストは Azure Active Directory から削除されず、Microsoft Teams 環境にも存在します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-155">When a team is deleted, guests are not removed from Azure Active Directory and as such still exist in the Microsoft Teams environment.</span></span> <span data-ttu-id="c68f9-156">ゲストは、グループ、サイト、チーム、またはそれらとの間で共有されていないコンテンツにアクセスできませんが、チャット、音声およびビデオ通話の開始、アプリの使用など、Microsoft Teams 内の機能を引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-156">While guests cannot access groups, sites, teams, or content which has not been shared with them, they can still potentially utilize features within Microsoft Teams such as initiating chats, voice and video calls, and using apps.</span></span>

<span data-ttu-id="c68f9-157">チームまたはグループの所有者は、外部ユーザーを招待して、Azure Active Directory のゲストにしたり、チームに追加したり、チームからそれらを削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-157">A team or group owner can invite an external user to become a guest in Azure Active Directory, add them to the team, as well as remove them from the team.</span></span> <span data-ttu-id="c68f9-158">ただし、チーム所有者は、Azure Active Directory からゲストを削除することはできません。これは、グローバル管理者またはユーザー管理者のみが実行できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-158">A team owner cannot, however, remove the guest from Azure Active Directory – this can only be performed by a global admin or user admin.</span></span>

<span data-ttu-id="c68f9-159">そのため、ゲストレビューを実行すること、およびチームの削除時に、ゲストを Azure Active Directory から削除する必要があるかどうかを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c68f9-159">Therefore it is important to perform guest reviews, as well as to understand whether guests need to be removed from Azure Active Directory upon team deletion.</span></span> <span data-ttu-id="c68f9-160">ゲストは、1つまたは複数の他のチームのメンバーである、または他の Microsoft 365 または Azure サービスを使用している場合など、ディレクトリに保持されるという有効なケースがあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-160">There may be a valid case for guests to remain in the directory, such as being a member of one or more other teams or using other Microsoft 365 or Azure services.</span></span>

## <a name="teams"></a><span data-ttu-id="c68f9-161">Teams</span><span class="sxs-lookup"><span data-stu-id="c68f9-161">Teams</span></span>

<span data-ttu-id="c68f9-162">Teams 固有のコンテンツは、主に会話の形式です。</span><span class="sxs-lookup"><span data-stu-id="c68f9-162">Teams-specific content is primarily in the form of conversations.</span></span>

<span data-ttu-id="c68f9-163">ネイティブの Microsoft Teams 機能を使用して、チャネル内の会話をコピーまたは移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-163">Conversations in channels cannot be copied or moved using native Microsoft Teams functionality.</span></span> <span data-ttu-id="c68f9-164">ただし、Graph API を使用してエクスポートすることはできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-164">They can however be exported using the Graph API.</span></span>

<span data-ttu-id="c68f9-165">また、アイテム保持ポリシーが Teams に適用されている場合、会話は保持され、電子情報開示の検索によって利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-165">Additionally, if a retention policy is applied to Teams, the conversations are retained and available through eDiscovery searches.</span></span> <span data-ttu-id="c68f9-166">(電子情報開示検索で見つかったアイテムはエクスポートできますが、元のソースからのコンテキストや構造は保持されないので、単に個々のメッセージになります)。</span><span class="sxs-lookup"><span data-stu-id="c68f9-166">(Items found in eDiscovery searches can be exported, however there no context or structure from their original source remains – they are simply individual messages.)</span></span>

### <a name="archiving-a-team"></a><span data-ttu-id="c68f9-167">チームをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="c68f9-167">Archiving a team</span></span>

<span data-ttu-id="c68f9-168">[チームをアーカイブ](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)する利点は、チームへのフルアクセスをユーザーが実行できるようにすることです。これにより、ユーザーは、チャネル会話を参照して、アクティブでない場合でもファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-168">The benefit of [archiving a team](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) is that it provides full access to the team as it was, so that users can still browse channel conversations and open files even if they are not active.</span></span> <span data-ttu-id="c68f9-169">また、チームで作業を続行する必要がある場合 (たとえば、プロジェクトの拡張機能など) に teams を unarchived ことができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-169">Additionally, teams can be unarchived if there is a need to continue working on them (such as in the case of a project extension).</span></span>

<span data-ttu-id="c68f9-170">所有者によってアーカイブされたチームは、チーム内のコンテンツと、関連付けられた SharePoint サイトの両方のメンバーに対して読み取り専用に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-170">When a team is archived by an owner, it is set to read-only for members both for content within the team as well as if selected, the associated SharePoint site.</span></span> <span data-ttu-id="c68f9-171">このアクションの目的は、チャネル内の会話が、ファイルや wiki などの SharePoint ベースのコンテンツと共に既存の状態で保持されるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="c68f9-171">The objective of this action is to ensure that conversations in channels are preserved in their existing state, along with SharePoint-based content such as files and wikis.</span></span>

<span data-ttu-id="c68f9-172">SharePoint サイトでは、表示された変更はありません。ただし、Microsoft 365 グループの SharePoint ベースのアクセス許可グループが [サイトの閲覧者] レベルに設定されている場合は、どのファイルまたはリストにも変更を加えることはできません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-172">In the SharePoint site there are no visible changes, however no changes can be made to any files or lists as the SharePoint-based permissions group for the Microsoft 365 Group is set to Site Visitors level.</span></span> <span data-ttu-id="c68f9-173">これには、SharePoint サイト内のサイトアセットライブラリに格納されているチームの OneNote ノートブックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-173">This includes the OneNote notebook for the team, as this is stored in the Site Assets library within the SharePoint site.</span></span>

<span data-ttu-id="c68f9-174">チームがアーカイブされている場合、基礎となる Microsoft 365 グループは、引き続き有効期限ポリシー (設定されている場合) の対象となるため、所有者は引き続きチームを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-174">When a team is archived, the underlying Microsoft 365 group is still subject to the expiration policy (if set), and as such the owner must continue to renew the team.</span></span>

<span data-ttu-id="c68f9-175">チームのチャネル会話と SharePoint サイトコンテンツは読み取り専用に設定されていますが、他の関連付けられているサービスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-175">While the team’s channel conversations and SharePoint site contents are set to read-only, the same is not applied to other associated services:</span></span>

- <span data-ttu-id="c68f9-176">Planner のバケットとタスクは、作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-176">Planner buckets and tasks can still be created, modified, and deleted</span></span>
- <span data-ttu-id="c68f9-177">フォームはまだ送信を受信できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-177">Forms can still receive submissions</span></span>
- <span data-ttu-id="c68f9-178">Outlook メールボックスでまだメールを受信できる</span><span class="sxs-lookup"><span data-stu-id="c68f9-178">The Outlook mailbox can still receive emails</span></span>
- <span data-ttu-id="c68f9-179">Power BI ダッシュボード、レポート、およびデータを変更できる</span><span class="sxs-lookup"><span data-stu-id="c68f9-179">Power BI dashboards, reports and data can still be modified</span></span>
- <span data-ttu-id="c68f9-180">プロジェクトとロードマップは、web 上の Project で引き続き編集できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-180">Projects and roadmaps can still be edited in Project on the web</span></span>
- <span data-ttu-id="c68f9-181">ストリーミングでビデオをアップロード、変更、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-181">Videos can still be uploaded, modified, and deleted in Stream</span></span>
- <span data-ttu-id="c68f9-182">パワー自動処理でのフローは、作成、変更、削除、および実行が続行されます (アーカイブされたチームのチャネルにメッセージを投稿するために必要な場合は失敗します)。</span><span class="sxs-lookup"><span data-stu-id="c68f9-182">Flows in Power Automate can still be created, modified, deleted, and will continue to run (they will fail however, if required to post a message to a channel of the archived team)</span></span>

## <a name="forms"></a><span data-ttu-id="c68f9-183">フォーム</span><span class="sxs-lookup"><span data-stu-id="c68f9-183">Forms</span></span>

<span data-ttu-id="c68f9-184">フォームを個別のアカウントからグループに移動することはできますが、グループ間で移動またはコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-184">While a form can be moved from an individual account to a group, it cannot be moved or copied from one group to another.</span></span> <span data-ttu-id="c68f9-185">チームを削除すると、フォームに使用できるオプションが3つあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-185">There are three options available for a form when a team is deleted.</span></span>

<span data-ttu-id="c68f9-186">**フォームを複製する**</span><span class="sxs-lookup"><span data-stu-id="c68f9-186">**Duplicate the form**</span></span>

<span data-ttu-id="c68f9-187">フォームを [テンプレートとして共有](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)でき、他のユーザーが自分のアカウントまたはグループにフォームをコピーできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c68f9-187">Forms can be [shared as templates](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), allowing other users to copy it to their own account or a group.</span></span> <span data-ttu-id="c68f9-188">これは、結果の送信からのデータを保持しません。質問や設定などのフォーム構造のみ</span><span class="sxs-lookup"><span data-stu-id="c68f9-188">This does not retain the data from result submissions; only form structure such as questions and settings.</span></span>

<span data-ttu-id="c68f9-189">**スプレッドシートに結果をエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-189">**Export results to a spreadsheet**</span></span>

<span data-ttu-id="c68f9-190">フォームへの応答のデータを保持する必要がある場合は、 [Excel スプレッドシートに結果をエクスポートする](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)ことで、これを実現できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-190">If the data of the form responses needs to be retained, this can be achieved by [exporting the results to an Excel spreadsheet](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af).</span></span> <span data-ttu-id="c68f9-191">これは、質問とその回答をデータとしてエクスポートするだけであり、フォームによって作成されたグラフは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-191">This will only export the questions and their responses as data – it does not include graphs created by Forms.</span></span>


<span data-ttu-id="c68f9-192">**フォームを削除する**</span><span class="sxs-lookup"><span data-stu-id="c68f9-192">**Delete the Form**</span></span>

<span data-ttu-id="c68f9-193">グループを削除すると、それに関連付けられているフォームも削除されますが、グループのメンバーはグループの所有者でなくても [直接削除](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) できます。ただし、これは、追加のメリットが提供されない手動の手順です。</span><span class="sxs-lookup"><span data-stu-id="c68f9-193">While deletion of the group will also result in the deletion of any associated forms, group members can [directly delete them](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) without being an owner of the group – however this is a manual step that does not provide any additional benefit.</span></span>

## <a name="onenote"></a><span data-ttu-id="c68f9-194">OneNote</span><span class="sxs-lookup"><span data-stu-id="c68f9-194">OneNote</span></span>

<span data-ttu-id="c68f9-195">グループに含まれる OneNote ノートブックは、関連付けられた SharePoint サイト内のサイトアセットライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-195">The OneNote notebook included in a group is stored in the Site Assets library within the associated SharePoint site.</span></span> <span data-ttu-id="c68f9-196">ノートブックファイルは複数の個別のファイルに分散されている場合がありますが、個別にコピーして開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-196">While notebook files can sometimes be spread across multiple individual files, they cannot be simply copied and opened independently.</span></span> <span data-ttu-id="c68f9-197">その代わりに、onenote ノートブックのコンテンツを OneNote 2016 を使用して移動またはエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-197">Instead, the contents of the OneNote notebook must be moved or exported using OneNote 2016.</span></span>

<span data-ttu-id="c68f9-198">**ページとセクションを別のノートブックに移動する**</span><span class="sxs-lookup"><span data-stu-id="c68f9-198">**Move pages and sections to another notebook**</span></span>

<span data-ttu-id="c68f9-199">[ページまたはセクションを個別に別のノートブックに移動](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) することで、所有者はデータをクリーンアップし、保持する必要のあるものだけを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-199">[Individually moving pages or sections to another notebook](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) provides owners with an opportunity to clean up their data and take only what needs to be retained.</span></span>

<span data-ttu-id="c68f9-200">**ノートブック全体をパッケージとしてエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-200">**Export the entire notebook as a package**</span></span>

<span data-ttu-id="c68f9-201">ノートブック全体を既存の構造と共に保持する必要がある場合は、 [OneNote パッケージファイルとしてエクスポート](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) してから、新しい場所にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-201">If the entire notebook needs to be retained with its existing structure, it can be [exported as a OneNote package](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) file and then imported to a new location.</span></span> <span data-ttu-id="c68f9-202">別の方法として、既存のマルチファイル構造ではなく1つのファイルに内容を保持する方法として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-202">Alternatively, this can be used as a method to retain the contents in a single file instead of the existing multi-file structure.</span></span>

<span data-ttu-id="c68f9-203">**PDF に印刷**</span><span class="sxs-lookup"><span data-stu-id="c68f9-203">**Print to PDF**</span></span>

<span data-ttu-id="c68f9-204">ノートブックの一部のコンテンツを参照用またはレコードとして保持する必要がある場合は、個々のページを [PDF に印刷して、別の場所に保存](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-204">In scenarios where some of the contents of the notebook need only to be retained for reference or as records, individual pages can be [printed to PDF and stored elsewhere](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).</span></span>

## <a name="mailbox-and-calendar"></a><span data-ttu-id="c68f9-205">メールボックスと予定表</span><span class="sxs-lookup"><span data-stu-id="c68f9-205">Mailbox and calendar</span></span>

<span data-ttu-id="c68f9-206">チームチャネル内で多くの会話が行われていたとしても、グループに関連付けられたメールボックスが使用されることは珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-206">It is not uncommon for the group-associated mailbox to be utilized, even though many conversations may have been conducted within team channels.</span></span> <span data-ttu-id="c68f9-207">メールボックスには、直接電子メールで送信されたメールは格納されず、チャネルに直接送信されたメールは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-207">The mailbox only stores emails that were emailed directly to it and does not include emails that were sent directly to channels.</span></span>

<span data-ttu-id="c68f9-208">場合によっては、メールボックス内に保存されている電子メールが、会議、Planner タスクの更新、その他のアプリまたはシステムによって生成されたメッセージの通知になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-208">In some cases, the emails stored within the mailbox may simply be notifications of meetings, Planner task updates, and other app or system generated messages.</span></span> <span data-ttu-id="c68f9-209">メールボックスの内容を確認して、コンテンツを保持または削除する必要があるかどうかを判断することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c68f9-209">It is important that the contents of the mailbox be reviewed to determine whether the content should be retained or deleted.</span></span>

<span data-ttu-id="c68f9-210">アイテム保持ポリシーが Exchange に適用されている場合は、電子メールと予定表のアイテムが保持され、電子情報開示検索によって利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-210">If a retention policy is applied to Exchange, the emails and calendar items are retained and available through eDiscovery searches.</span></span>

<span data-ttu-id="c68f9-211">**メールと予定表をエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-211">**Export mail and calendar**</span></span>

<span data-ttu-id="c68f9-212">チームまたはグループのメンバーは、 [メールボックスと予定表の内容を Outlook Data/Personal Storage (PST) ファイルにエクスポート](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-212">Team or group members can [export the contents of the mailbox and calendar to an Outlook Data / Personal Storage (PST) file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91).</span></span> <span data-ttu-id="c68f9-213">このファイルは、他の場所に保存することも、別のメールボックスにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-213">This file can then be stored elsewhere, or the contents can be imported into a different mailbox.</span></span> <span data-ttu-id="c68f9-214">PST ファイルのコンテンツを Outlook で開くことなく検索できないため、前者は推奨されません。ファイル自体は、時間の経過とともに破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-214">The former is not recommended as the contents of the PST file are not searchable without opening it in Outlook, and the file itself can become corrupted over time.</span></span>

<span data-ttu-id="c68f9-215">**IT で実行されるコンテンツの移行**</span><span class="sxs-lookup"><span data-stu-id="c68f9-215">**IT-performed content migration**</span></span>

<span data-ttu-id="c68f9-216">管理者はサードパーティ製のツールを使用して、ユーザーの介入なしにメールボックスと予定表の内容を移行することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-216">Administrators can use third-party tools to migrate email and calendar contents between mailboxes without any user intervention.</span></span> <span data-ttu-id="c68f9-217">格納場所として考えられるのは、単にグループメールボックスの内容の "アーカイブ" として機能するように作成された共有メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="c68f9-217">One potential storage location could be a shared mailbox created purely to serve as an “archive” of the group mailbox contents.</span></span>

## <a name="planner"></a><span data-ttu-id="c68f9-218">Planner</span><span class="sxs-lookup"><span data-stu-id="c68f9-218">Planner</span></span>

<span data-ttu-id="c68f9-219">各グループまたはチームは、複数のプランを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-219">Each group or team can have multiple plans.</span></span> <span data-ttu-id="c68f9-220">オフボードプロセスにおいて、そのコンテンツが保持されているかどうかに応じて各プランが確実に処理されるようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="c68f9-220">It is important during the offboarding process to ensure that each plan is addressed as to whether its contents are retained.</span></span> <span data-ttu-id="c68f9-221">他の製品と同様に、Planner には、オフボードコンテンツに対するいくつかのアプローチがあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-221">Like the other products, there are several approaches to offboard content in Planner.</span></span>

<span data-ttu-id="c68f9-222">**プランをスプレッドシートにエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-222">**Export the plan to a spreadsheet**</span></span>

<span data-ttu-id="c68f9-223">レコード保持のための計画のコピーを保持する必要があるだけの場合、最も簡単な方法は、 [計画を Excel スプレッドシートにエクスポート](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)することです。</span><span class="sxs-lookup"><span data-stu-id="c68f9-223">If it is only required to keep a copy of the plan for record-keeping purposes, the simplest approach is to [export the plan to an Excel spreadsheet](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a).</span></span> <span data-ttu-id="c68f9-224">これは、スプレッドシートからプランをインポートするオプションがないので、一ウェイのアクションです。</span><span class="sxs-lookup"><span data-stu-id="c68f9-224">This is a one-way action, as there is no option to import plans from a spreadsheet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c68f9-225">プランを Excel にエクスポートする場合は、プラン内でほとんどの情報が取得されますが、コメント、リンク、またはファイルは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-225">Exporting a plan to Excel will take most information within the plan, but will not include comments, links, or files.</span></span>

<span data-ttu-id="c68f9-226">**タスクを別のプランにコピーして移動する**</span><span class="sxs-lookup"><span data-stu-id="c68f9-226">**Copy and move tasks to another Plan**</span></span>

<span data-ttu-id="c68f9-227">これはソリューションのように思えますが、個々のタスクは同じグループ内の [プラン間でのみコピーまたは移動](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) できます。これにより、プランに関連付けられたグループが削除されている場合のメリットがなくなります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-227">While this seems like a solution, individual tasks can only be [copied or moved between plans](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) within the same group, which negates the benefit in if the group associated With the plan is being deleted.</span></span>

<span data-ttu-id="c68f9-228">**プラン全体のコピー**</span><span class="sxs-lookup"><span data-stu-id="c68f9-228">**Copy entire plan**</span></span>

<span data-ttu-id="c68f9-229">[プラン全体をコピー](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)することもできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-229">It is also possible to [copy the entire plan](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4).</span></span> <span data-ttu-id="c68f9-230">ただし、これは既存のグループ、または同じグループ内にあってはなりません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-230">However this cannot be to an existing group or even within the same group.</span></span> <span data-ttu-id="c68f9-231">計画をコピーすると、新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-231">Copying the plan will create a new group.</span></span> <span data-ttu-id="c68f9-232">また、計画全体のコピーには、コメント、割り当て、リンク、添付ファイル、または日付は含まれません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-232">Additionally, copying the entire plan will not include comments, assignments, links, attachments, or dates.</span></span>

## <a name="power-automate"></a><span data-ttu-id="c68f9-233">Power Automate</span><span class="sxs-lookup"><span data-stu-id="c68f9-233">Power Automate</span></span>

<span data-ttu-id="c68f9-234">電力の自動化によって作成され、グループまたはチームに関連付けられているフローはグループに属しておらず、その代わりに所有者が所有し、他のユーザーやグループとのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-234">Flows created in Power Automate and associated with a group or team do not belong to the group, and instead are owned by the creator and merely shared with other users and groups.</span></span> <span data-ttu-id="c68f9-235">そのような場合、グループまたはチームが削除されても影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-235">As such they are not affected if a group or team is deleted.</span></span>

<span data-ttu-id="c68f9-236">**フローの所有権を変更する**</span><span class="sxs-lookup"><span data-stu-id="c68f9-236">**Change ownership of the flow**</span></span>

<span data-ttu-id="c68f9-237">ワークフローの操作を続行する必要がある場合、所有者は、他のユーザーまたは Microsoft 365 グループを所有者として追加するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-237">If the workflow needs to continue operating, any owners can simply add other users or Microsoft 365 groups as owners.</span></span>

<span data-ttu-id="c68f9-238">**フローをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-238">**Export the flow**</span></span>

<span data-ttu-id="c68f9-239">ワークフローの運用を続行する必要はありませんが、将来の使用のために保持する必要がある場合は、 [ファイルとしてエクスポート](https://flow.microsoft.com/blog/import-export-bap-packages/) し、後でもう一度インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-239">If the workflow does not need to continue operating but it needs to be preserved for potential future use, it can be [exported as a file](https://flow.microsoft.com/blog/import-export-bap-packages/) and imported again later.</span></span>

## <a name="power-bi"></a><span data-ttu-id="c68f9-240">Power BI</span><span class="sxs-lookup"><span data-stu-id="c68f9-240">Power BI</span></span>

<span data-ttu-id="c68f9-241">Power BI データとワークスペースは、グループやチームとは独立して運用できます。また、他のワークロードと同様に、さまざまな方法で offboarded することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-241">Power BI data and workspaces can operate independently from groups and teams and like other workloads offer different ways of being offboarded.</span></span>

<span data-ttu-id="c68f9-242">**レポートを別のワークスペースにコピーする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-242">**Copy reports to another workspace**</span></span>

<span data-ttu-id="c68f9-243">グループまたはチームの寿命を超えてレポートを機能状態に保持する必要がある場合は、 [POWER BI 内の既存のワークスペースから別のワークスペースにコピー](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-243">If the report needs to be preserved in its functional state beyond the life of the group or team, it can be [copied from the existing workspace to another workspace within Power BI](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).</span></span>

<span data-ttu-id="c68f9-244">**ダッシュボードまたはレポートからデータをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-244">**Export data from a dashboard or report**</span></span>

<span data-ttu-id="c68f9-245">または、レポートをアクティブにする必要がなく、データを保持する必要がある場合は、 [Excel にエクスポート](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)することもできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-245">Alternatively, if the report no longer needs to be active but the data needs to be retained, it can be [exported to Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>

## <a name="project"></a><span data-ttu-id="c68f9-246">Project</span><span class="sxs-lookup"><span data-stu-id="c68f9-246">Project</span></span>

<span data-ttu-id="c68f9-247">Web 上の Project で作成されたプロジェクトとロードマップは、Microsoft 365 グループに関連付けることができ、Power BI に似たオフボードへのアプローチを提供します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-247">Projects and Roadmaps created in Project on the web can be associated with Microsoft 365 groups and offers approaches to offboarding similar to Power BI.</span></span>

<span data-ttu-id="c68f9-248">**プロジェクトを別のグループに割り当てる**</span><span class="sxs-lookup"><span data-stu-id="c68f9-248">**Assign the project to another group**</span></span>

<span data-ttu-id="c68f9-249">プロジェクトをグループまたはチームの寿命を超えて機能している状態で保持する必要がある場合は、Dynamics 365 管理センターを使用して、 [別の Microsoft 365 グループに割り当てる](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) ことができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-249">If the project needs to be preserved in its functional state beyond the life of the group or team, it can be [assigned to a different Microsoft 365 group](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) using the Dynamics 365 Administration Center.</span></span>

<span data-ttu-id="c68f9-250">**プロジェクトまたはロードマップからデータをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-250">**Export data from the project or roadmap**</span></span>

<span data-ttu-id="c68f9-251">Dynamics 365 管理センターを使用すると、 [ユーザーデータをプロジェクトから](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) スプレッドシートにエクスポートできます。または、PowerShell スクリプトを使用すると、データをプロジェクトファイル () にエクスポートできます。MPP) および XML ファイル形式。</span><span class="sxs-lookup"><span data-stu-id="c68f9-251">Using the Dynamics 365 Administration Center it is possible to [export user data from the project](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) to a spreadsheet, or if using a PowerShell script the data can be exported to Project file (.MPP) and XML file formats.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="c68f9-252">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c68f9-252">SharePoint</span></span>
<span data-ttu-id="c68f9-253">チームチャネル内のすべてのファイルは、関連付けられたグループの SharePoint サイトのドキュメントライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-253">All files in team channels are stored in the document library in the SharePoint site of the associated group.</span></span> <span data-ttu-id="c68f9-254">場合によっては、リストやページなど、ドキュメント以外のコンテンツが SharePoint に存在することがあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-254">In some cases, content other than documents may exist in SharePoint, such as lists or pages.</span></span>
<span data-ttu-id="c68f9-255">通常、ファイルは SharePoint サイト内の3つの主要な場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-255">Files are generally stored in three primary locations within a SharePoint site:</span></span>

- <span data-ttu-id="c68f9-256">ページ-サイトページライブラリ</span><span class="sxs-lookup"><span data-stu-id="c68f9-256">Pages - Site Pages library</span></span>
- <span data-ttu-id="c68f9-257">ページで使用される画像–サイトアセットライブラリ</span><span class="sxs-lookup"><span data-stu-id="c68f9-257">Images used in pages – Site Assets library</span></span>
- <span data-ttu-id="c68f9-258">チャネル内のファイル–ドキュメントライブラリ</span><span class="sxs-lookup"><span data-stu-id="c68f9-258">Files in channels – Documents library</span></span>
- <span data-ttu-id="c68f9-259">Wiki ページ– Teams Wiki データライブラリ</span><span class="sxs-lookup"><span data-stu-id="c68f9-259">Wiki pages – Teams Wiki Data library</span></span>

<span data-ttu-id="c68f9-260">サイトの下位に1つ以上のサブサイトが入れ子になっている場合は、各サブサイトでオフボードプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-260">If the site has one or more sub-sites nested underneath it, the offboarding process will need to be repeated for each sub-site.</span></span> <span data-ttu-id="c68f9-261">チームにプライベートチャネルが含まれている場合は、チャネルごとに独立した SharePoint サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="c68f9-261">If the team contains private channels, there is a separate SharePoint site for each channel.</span></span>

<span data-ttu-id="c68f9-262">グループまたはチームからファイルを削除する場合は、グループまたはチームのメンバーではないユーザー (組織の内部または外部のいずれか) との間で共有されている可能性があるため、そのような変更をより簡単に伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-262">It is important when removing files from a group or team to consider that they may be shared with users who are not members of the group or team (whether internal or external to the organization), and as such it may be worthwhile communicating the impending change to them.</span></span>

<span data-ttu-id="c68f9-263">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-263">**Download files**</span></span>

<span data-ttu-id="c68f9-264">前述のライブラリのいずれかで SharePoint に格納されたファイルの場合は、 [ローカルコンピューターにダウンロード](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-264">In the case of files stored within SharePoint in one of the libraries mentioned above, these can be [downloaded to a local computer](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span>

<span data-ttu-id="c68f9-265">**ファイルの移動**</span><span class="sxs-lookup"><span data-stu-id="c68f9-265">**Move files**</span></span>

<span data-ttu-id="c68f9-266">さらに、別のサイトのライブラリなど、SharePoint 内の別の場所にファイルを移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-266">Additionally, files can be moved to another location within SharePoint such as a library in a different site.</span></span>
<span data-ttu-id="c68f9-267">参考 https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc</span><span class="sxs-lookup"><span data-stu-id="c68f9-267">Reference: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc</span></span>

<span data-ttu-id="c68f9-268">**リストのエクスポート** SharePoint リスト内に格納されているデータは、 [Excel スプレッドシートにエクスポート](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)して、別のサイトのリストに再度インポートできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-268">**Export list** Data stored within SharePoint lists can be [exported to an Excel spreadsheet](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9), and imported again to a list in another site.</span></span>

<span data-ttu-id="c68f9-269">または、関数、リストビュー、書式設定、およびその他の属性を保持するために、サードパーティ製ツールを使用してサイト間でリストを移行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-269">Alternatively, a third-party tool can be used to migrate the list between sites in order to retain function, list views, formatting, and other attributes.</span></span>

<span data-ttu-id="c68f9-270">**Wiki ファイルをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-270">**“Export” wiki files**</span></span>

<span data-ttu-id="c68f9-271">チームチャネル内の Wiki コンテンツは、関連付けられた SharePoint サイトの専用ライブラリ内の HTML 形式のファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-271">Wiki contents within team channels are stored in a HTML formatted file in a dedicated library of the associated SharePoint site.</span></span> <span data-ttu-id="c68f9-272">これらは、簡単にエクスポートして別の channel wiki にインポートすることはできませんが、HTML ファイルに変換して web ページとして開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-272">They cannot be readily exported and imported to another channel wiki but can be converted to a HTML file and opened as a web page.</span></span>

## <a name="microsoft-stream"></a><span data-ttu-id="c68f9-273">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="c68f9-273">Microsoft Stream</span></span>

<span data-ttu-id="c68f9-274">電源自動化と同様に、グループまたはチームに関連付けられたストリーム内のビデオは、実際にはグループによって所有されず、グループの削除時にも削除されません。</span><span class="sxs-lookup"><span data-stu-id="c68f9-274">Like Power Automate, videos in Stream associated with a group or team are not actually owned by the group and are not deleted when the group is deleted.</span></span> <span data-ttu-id="c68f9-275">ストリーム内のビデオは、ユーザーまたはグループを所有者として追加した場合でも、ビデオをアップロードまたは作成したユーザーによって所有されます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-275">Videos in Stream are owned by the person who uploaded or created the video, even if they add users or groups as owners.</span></span> <span data-ttu-id="c68f9-276">これは、Teams チャネルに記録された会議の場合にも当てはまります。レコーディングを開始したユーザーによって所有されている。</span><span class="sxs-lookup"><span data-stu-id="c68f9-276">This is also the case for meetings recorded in a Teams channel; they are owned by the person who initiated the recording.</span></span>

<span data-ttu-id="c68f9-277">**他の所有者の追加**</span><span class="sxs-lookup"><span data-stu-id="c68f9-277">**Adding other owners**</span></span>

<span data-ttu-id="c68f9-278">グループの削除に関係なく、ビデオが Stream に保持されるため、元の所有者は、 [そのビデオを所有者として追加しても、他のユーザーやグループと共有](https://docs.microsoft.com/stream/portal-edit-video)できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-278">As the video is retained in Stream regardless of group deletion, the original owner can [share the video with other users and groups, even adding them as owners](https://docs.microsoft.com/stream/portal-edit-video).</span></span>

<span data-ttu-id="c68f9-279">**ビデオをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-279">**Download the video**</span></span>

<span data-ttu-id="c68f9-280">ビデオをストリームで保持する必要がない場合、またはレコード管理システムなどの代替の場所に保存する必要がある場合は、所有者が[ローカルにダウンロード](https://docs.microsoft.com/stream/portal-download-video)することができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-280">In scenarios where the video does not need to be retained in Stream or needs to be stored in an alternate location such as a records management system, an owner can be [download it locally](https://docs.microsoft.com/stream/portal-download-video)</span></span>

## <a name="yammer"></a><span data-ttu-id="c68f9-281">Yammer</span><span class="sxs-lookup"><span data-stu-id="c68f9-281">Yammer</span></span>

<span data-ttu-id="c68f9-282">Microsoft Teams の会話とは異なり、Yammer は会話を移動またはエクスポートするためのユーザーと管理者の両方のオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="c68f9-282">Unlike conversations in Microsoft Teams, Yammer offers both users and administrators options to move or export conversations.</span></span>

<span data-ttu-id="c68f9-283">**会話を別のグループまたはコミュニティに移動する**</span><span class="sxs-lookup"><span data-stu-id="c68f9-283">**Move conversations to another group or community**</span></span>

<span data-ttu-id="c68f9-284">会話は、所有者や管理者だけでなく、任意のユーザーによって別の Yammer グループに移動できます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-284">Conversations can be moved to another Yammer group by any user, not just owners or administrators.</span></span> <span data-ttu-id="c68f9-285">これは、 [クラシック yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)と [新しい yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) インターフェイスの両方で可能です。</span><span class="sxs-lookup"><span data-stu-id="c68f9-285">This is possible in both the [classic Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872), as well as the [new Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) interfaces.</span></span>

<span data-ttu-id="c68f9-286">**ネットワークデータをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="c68f9-286">**Export network data**</span></span>

<span data-ttu-id="c68f9-287">Yammer ネットワーク管理者は [ネットワークデータのエクスポート](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)を実行できますが、これにより、ネットワーク全体のすべての会話がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-287">Yammer network administrators can perform an [export of network data](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data), however doing so will export all conversations for the entire network.</span></span> <span data-ttu-id="c68f9-288">結果のエクスポートではグループ ID が一覧表示されるので、これに基づいて会話にフィルターをかけることができます。</span><span class="sxs-lookup"><span data-stu-id="c68f9-288">The resulting export however lists the Group ID, so it is possible to filter conversations based on this.</span></span>
