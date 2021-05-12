---
title: グループ、チーム、およびグループのライフサイクルのYammer
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
description: グループ、チーム、およびグループのライフサイクルのYammer。
ms.openlocfilehash: f1f91e64af7e16016398a7c326feec5a9b073ca9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333784"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a><span data-ttu-id="4b53d-103">グループ、チーム、およびグループのライフサイクルのYammer</span><span class="sxs-lookup"><span data-stu-id="4b53d-103">End of lifecycle options for groups, teams, and Yammer</span></span>

<span data-ttu-id="4b53d-104">Microsoft 365 グループと Microsoft Teams は、さまざまな接続サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-104">Microsoft 365 Groups and Microsoft Teams work with a variety of connected services.</span></span> <span data-ttu-id="4b53d-105">グループまたはチームが削除されると、接続されているサービスのほとんどの情報も削除されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-105">When a group or team is deleted, most of the information in the connected services is also deleted.</span></span> <span data-ttu-id="4b53d-106">この記事では、削除前にグループまたはチームから情報を移動して情報を保持するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-106">This article describes options for retaining information by moving it out of the group or team prior to deletion.</span></span>

<span data-ttu-id="4b53d-107">不要になったグループやチームの一般的な方法は、ファイルをチームから移動し、リポジトリやアーカイブとして機能する SharePoint ドキュメント ライブラリなどの別の場所に保存する方法です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-107">A common practice for groups or teams that are no longer required is to move the files out of the team and store them in another location such as a SharePoint document library acting as a repository or archive.</span></span> <span data-ttu-id="4b53d-108">この方法は、ファイルやフォルダー内に情報が格納され、電子メールを介して通信が行われる従来のスタイルの作業に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-108">This practice is based on a legacy style of working where information is stored within files and folders, and communications are conducted via email.</span></span>

<span data-ttu-id="4b53d-109">次の表に、グループとチームに関連付けられているサービスと、各グループで見つかった主要な種類のコンテンツの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-109">The following table outlines the services associated with groups and teams and key types of content found in each of them:</span></span>

|<span data-ttu-id="4b53d-110">サービス</span><span class="sxs-lookup"><span data-stu-id="4b53d-110">Service</span></span>|<span data-ttu-id="4b53d-111">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="4b53d-111">Types of content</span></span>|
|:------|:---------------|
|<span data-ttu-id="4b53d-112">Teams</span><span class="sxs-lookup"><span data-stu-id="4b53d-112">Teams</span></span>|<span data-ttu-id="4b53d-113">チャネルの会話、チャネル内のファイル</span><span class="sxs-lookup"><span data-stu-id="4b53d-113">Channel conversations, files in channels</span></span>|
|<span data-ttu-id="4b53d-114">フォーム</span><span class="sxs-lookup"><span data-stu-id="4b53d-114">Forms</span></span>|<span data-ttu-id="4b53d-115">アンケートの構造と結果</span><span class="sxs-lookup"><span data-stu-id="4b53d-115">Survey structure and results</span></span>|
|<span data-ttu-id="4b53d-116">OneNote</span><span class="sxs-lookup"><span data-stu-id="4b53d-116">OneNote</span></span>|<span data-ttu-id="4b53d-117">Notebook</span><span class="sxs-lookup"><span data-stu-id="4b53d-117">Notebook</span></span>|
|<span data-ttu-id="4b53d-118">Outlook</span><span class="sxs-lookup"><span data-stu-id="4b53d-118">Outlook</span></span>|<span data-ttu-id="4b53d-119">メールと予定表</span><span class="sxs-lookup"><span data-stu-id="4b53d-119">Mail and calendar</span></span>|
|<span data-ttu-id="4b53d-120">Planner</span><span class="sxs-lookup"><span data-stu-id="4b53d-120">Planner</span></span>|<span data-ttu-id="4b53d-121">プロジェクトの状態とタスク情報</span><span class="sxs-lookup"><span data-stu-id="4b53d-121">Project status and task information</span></span>|
|<span data-ttu-id="4b53d-122">Power Automate</span><span class="sxs-lookup"><span data-stu-id="4b53d-122">Power Automate</span></span>|<span data-ttu-id="4b53d-123">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="4b53d-123">Workflows</span></span>|
|<span data-ttu-id="4b53d-124">Power BI</span><span class="sxs-lookup"><span data-stu-id="4b53d-124">Power BI</span></span>|<span data-ttu-id="4b53d-125">データ、レポート、ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="4b53d-125">Data, reports, and dashboards</span></span>|
|<span data-ttu-id="4b53d-126">Web 上のプロジェクト</span><span class="sxs-lookup"><span data-stu-id="4b53d-126">Project on the web</span></span>|<span data-ttu-id="4b53d-127">プロジェクト計画</span><span class="sxs-lookup"><span data-stu-id="4b53d-127">Project plans</span></span>|
|<span data-ttu-id="4b53d-128">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="4b53d-128">Roadmap</span></span>|<span data-ttu-id="4b53d-129">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="4b53d-129">Roadmaps</span></span>|
|<span data-ttu-id="4b53d-130">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b53d-130">SharePoint</span></span>|<span data-ttu-id="4b53d-131">ファイル、リスト、Teams チャネル Wiki データ</span><span class="sxs-lookup"><span data-stu-id="4b53d-131">Files, lists, Teams channel wiki data</span></span>|
|<span data-ttu-id="4b53d-132">Stream</span><span class="sxs-lookup"><span data-stu-id="4b53d-132">Stream</span></span>|<span data-ttu-id="4b53d-133">ビデオ</span><span class="sxs-lookup"><span data-stu-id="4b53d-133">Videos</span></span>|
|<span data-ttu-id="4b53d-134">Yammer</span><span class="sxs-lookup"><span data-stu-id="4b53d-134">Yammer</span></span>|<span data-ttu-id="4b53d-135">会話</span><span class="sxs-lookup"><span data-stu-id="4b53d-135">Conversations</span></span>|

<span data-ttu-id="4b53d-136">グループまたはチームを削除すると、関連付けられているリソースのほとんども削除されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-136">When deleting a group or team, most of the associated resources are also deleted.</span></span> <span data-ttu-id="4b53d-137">この例外の一部には、Stream のビデオが含まれます。これらは残り、Power Automate のフローと同様に、アップロードまたは記録したユーザーが所有しています。</span><span class="sxs-lookup"><span data-stu-id="4b53d-137">Some of the exceptions to this include videos in Stream – these remain and are still owned by the person who uploaded/recorded them, as do flows in Power Automate.</span></span> <span data-ttu-id="4b53d-138">Project on the web のプロジェクトデータとロードマップ データは CDS に残り、個別に復元できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-138">Project and roadmap data in Project on the web remains in the CDS and can be restored separately.</span></span>

<span data-ttu-id="4b53d-139">グループとチームは 30 日間、ソフト削除状態のままであり、いつでも復元できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-139">Groups and teams remain in a soft-delete state for 30 days and can be restored at any time.</span></span> <span data-ttu-id="4b53d-140">ただし、30 日後、サービスやコンテンツなどの関連リソースは、Microsoft 365 環境から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-140">However, after the 30 days they, and any associated resources such as services and content, are completely purged from the Microsoft 365 environment.</span></span> <span data-ttu-id="4b53d-141">アイテム保持ポリシーで保護されているコンテンツは、電子情報開示検索を通じて引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-141">Any content protected by a retention policy remains available through eDiscovery searches.</span></span>

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a><span data-ttu-id="4b53d-142">グループ接続サービスのライフ サイクルの終了に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4b53d-142">End of life cycle considerations for group-connected services</span></span>

<span data-ttu-id="4b53d-143">グループまたはチームを削除する際には、チームとグループの所有者と IT 管理者が考慮する必要がある 3 つの重要な領域があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-143">There are three key areas that team and group owners and IT administrators need to consider when deleting a group or team.</span></span>

<span data-ttu-id="4b53d-144">**Content**</span><span class="sxs-lookup"><span data-stu-id="4b53d-144">**Content**</span></span>

<span data-ttu-id="4b53d-145">チームが機能しなくなった後、または存在した後にコンテンツを保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="4b53d-145">Does the content need to be retained after the team is no longer functional or in existence?</span></span> <span data-ttu-id="4b53d-146">Microsoft 365 の保持機能に依存して十分ですか、それとも保持を提供しないアプリやサービスのコンテンツの一部ですか?</span><span class="sxs-lookup"><span data-stu-id="4b53d-146">Is it sufficient to rely on retention capabilities of Microsoft 365, or is some of the content in apps and services that do not offer retention?</span></span> <span data-ttu-id="4b53d-147">コンテンツは、レコード管理目的、アーカイブ目的、または将来の使用および参照の目的で保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="4b53d-147">Does the content need to be retained for record management purposes, for archival purposes, or for future use and reference purposes?</span></span>

<span data-ttu-id="4b53d-148">これらの質問は、潜在的なデータ損失を回避するために、チームがアーカイブまたは削除される前に質問する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-148">These questions must be asked before any team is archived or deleted, to avoid any potential data loss.</span></span>

<span data-ttu-id="4b53d-149">**サービス**</span><span class="sxs-lookup"><span data-stu-id="4b53d-149">**Services**</span></span>

<span data-ttu-id="4b53d-150">さまざまなアプリやサービスのコンテンツの上に、現在の作業フォームに残る必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="4b53d-150">On top of the content across various apps and services, do they need to stay in their current working form?</span></span> <span data-ttu-id="4b53d-151">たとえば、Power BI レポートに引き続きアクセスできる必要がありますか、フォームの結果を視覚的な概要ビューで使用できる必要がありますか、SharePoint のリストはリンクされているのか、どこに埋め込まれているのか。</span><span class="sxs-lookup"><span data-stu-id="4b53d-151">For example, does the Power BI report need to continue to be accessible, do the Form results need to be available in the visual summary view, are the lists in SharePoint linked to or embedded anywhere?</span></span>

<span data-ttu-id="4b53d-152">コンテンツの考慮事項と同様に、コンテンツをエクスポートするだけでは十分ではない可能性があるとして、基になるグループを削除する前に、これらの質問を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-152">Similar to the content considerations, these questions must be asked before the underlying group is deleted as simply exporting the content may not be sufficient.</span></span>

<span data-ttu-id="4b53d-153">**ゲスト**</span><span class="sxs-lookup"><span data-stu-id="4b53d-153">**Guests**</span></span>

<span data-ttu-id="4b53d-154">ゲストをチームに招待すると、ワークフローはホスト組織の Azure Active Directory に ID を作成してからチームに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-154">When guests are invited to a team, the workflow creates their identity in the host organization’s Azure Active Directory before adding them to the team.</span></span> <span data-ttu-id="4b53d-155">チームが削除されると、ゲストは Azure Active Directory から削除されないので、Microsoft Teams 環境に存在します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-155">When a team is deleted, guests are not removed from Azure Active Directory and as such still exist in the Microsoft Teams environment.</span></span> <span data-ttu-id="4b53d-156">ゲストはグループ、サイト、チーム、または共有されていないコンテンツにアクセスできませんが、チャット、音声通話、ビデオ通話の開始、アプリの使用など、Microsoft Teams 内の機能を利用できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-156">While guests cannot access groups, sites, teams, or content which has not been shared with them, they can still potentially utilize features within Microsoft Teams such as initiating chats, voice and video calls, and using apps.</span></span>

<span data-ttu-id="4b53d-157">チームまたはグループの所有者は、外部ユーザーを Azure Active Directory のゲストに招待し、チームに追加し、チームから削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-157">A team or group owner can invite an external user to become a guest in Azure Active Directory, add them to the team, as well as remove them from the team.</span></span> <span data-ttu-id="4b53d-158">ただし、チームの所有者は Azure Active Directory からゲストを削除できません。これは、グローバル管理者またはユーザー管理者によってのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-158">A team owner cannot, however, remove the guest from Azure Active Directory – this can only be performed by a global admin or user admin.</span></span>

<span data-ttu-id="4b53d-159">したがって、ゲスト レビューを実行し、チームの削除時にゲストを Azure Active Directory から削除する必要があるかどうかを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-159">Therefore it is important to perform guest reviews, as well as to understand whether guests need to be removed from Azure Active Directory upon team deletion.</span></span> <span data-ttu-id="4b53d-160">1 つ以上の他のチームのメンバーであることや、他の Microsoft 365 または Azure サービスを使用する場合など、ゲストがディレクトリに残る場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-160">There may be a valid case for guests to remain in the directory, such as being a member of one or more other teams or using other Microsoft 365 or Azure services.</span></span>

## <a name="teams"></a><span data-ttu-id="4b53d-161">Teams</span><span class="sxs-lookup"><span data-stu-id="4b53d-161">Teams</span></span>

<span data-ttu-id="4b53d-162">Teams 固有のコンテンツは、主に会話の形式です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-162">Teams-specific content is primarily in the form of conversations.</span></span>

<span data-ttu-id="4b53d-163">チャネル内の会話は、Microsoft Teams のネイティブ機能を使用してコピーまたは移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-163">Conversations in channels cannot be copied or moved using native Microsoft Teams functionality.</span></span> <span data-ttu-id="4b53d-164">ただし、Graph API を使用してエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-164">They can however be exported using the Graph API.</span></span>

<span data-ttu-id="4b53d-165">さらに、アイテム保持ポリシーが Teams に適用されている場合、会話は保持され、電子情報開示検索によって利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-165">Additionally, if a retention policy is applied to Teams, the conversations are retained and available through eDiscovery searches.</span></span> <span data-ttu-id="4b53d-166">高度な電子情報開示を使用すると [、Teams チャットの会話を再構築できます](/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-166">Using advanced eDiscovery you can [reconstruct a Teams chat conversation](/microsoft-365/compliance/conversation-review-sets).</span></span>


### <a name="archiving-a-team"></a><span data-ttu-id="4b53d-167">チームのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="4b53d-167">Archiving a team</span></span>

<span data-ttu-id="4b53d-168">チームを [アーカイブする](/microsoftteams/archive-or-delete-a-team) 利点は、チームにフル アクセスを提供し、ユーザーがアクティブでなくてもチャネルの会話やファイルを開くことができるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-168">The benefit of [archiving a team](/microsoftteams/archive-or-delete-a-team) is that it provides full access to the team as it was, so that users can still browse channel conversations and open files even if they are not active.</span></span> <span data-ttu-id="4b53d-169">さらに、チームの作業を続行する必要がある場合 (プロジェクト拡張機能の場合など) は、チームをアーカイブ解除できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-169">Additionally, teams can be unarchived if there is a need to continue working on them (such as in the case of a project extension).</span></span>

<span data-ttu-id="4b53d-170">チームが所有者によってアーカイブされている場合、チーム内のコンテンツと、関連付けられた SharePoint サイトが選択されている場合の両方のメンバーの読み取り専用に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-170">When a team is archived by an owner, it is set to read-only for members both for content within the team as well as if selected, the associated SharePoint site.</span></span> <span data-ttu-id="4b53d-171">このアクションの目的は、チャネル内の会話がファイルや Wiki などの SharePoint ベースのコンテンツと共に、既存の状態で保持される状態を維持する方法です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-171">The objective of this action is to ensure that conversations in channels are preserved in their existing state, along with SharePoint-based content such as files and wikis.</span></span>

<span data-ttu-id="4b53d-172">SharePoint サイトでは目に見える変更はありません。ただし、Microsoft 365 グループの SharePoint ベースのアクセス許可グループがサイト訪問者レベルに設定されている場合、ファイルやリストに変更を加えすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-172">In the SharePoint site there are no visible changes, however no changes can be made to any files or lists as the SharePoint-based permissions group for the Microsoft 365 Group is set to Site Visitors level.</span></span> <span data-ttu-id="4b53d-173">これには、チームの OneNote ノートブックが含まれます。これは SharePoint サイト内の Site Assets ライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-173">This includes the OneNote notebook for the team, as this is stored in the Site Assets library within the SharePoint site.</span></span>

<span data-ttu-id="4b53d-174">チームがアーカイブされている場合、基になる Microsoft 365 グループは有効期限ポリシー (設定されている場合) の対象であり、所有者は引き続きチームを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-174">When a team is archived, the underlying Microsoft 365 group is still subject to the expiration policy (if set), and as such the owner must continue to renew the team.</span></span>

<span data-ttu-id="4b53d-175">チームのチャネル会話と SharePoint サイトのコンテンツは読み取り専用に設定されているが、他の関連サービスにも同じ内容は適用されません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-175">While the team’s channel conversations and SharePoint site contents are set to read-only, the same is not applied to other associated services:</span></span>

- <span data-ttu-id="4b53d-176">Planner バケットとタスクは、引き続き作成、変更、削除できます</span><span class="sxs-lookup"><span data-stu-id="4b53d-176">Planner buckets and tasks can still be created, modified, and deleted</span></span>
- <span data-ttu-id="4b53d-177">フォームは引き続き申請を受け取ることができます</span><span class="sxs-lookup"><span data-stu-id="4b53d-177">Forms can still receive submissions</span></span>
- <span data-ttu-id="4b53d-178">Outlook メールボックスは引き続き電子メールを受信できます</span><span class="sxs-lookup"><span data-stu-id="4b53d-178">The Outlook mailbox can still receive emails</span></span>
- <span data-ttu-id="4b53d-179">Power BI ダッシュボード、レポート、およびデータは変更できます</span><span class="sxs-lookup"><span data-stu-id="4b53d-179">Power BI dashboards, reports and data can still be modified</span></span>
- <span data-ttu-id="4b53d-180">プロジェクトとロードマップは、Web 上の Project で編集できます</span><span class="sxs-lookup"><span data-stu-id="4b53d-180">Projects and roadmaps can still be edited in Project on the web</span></span>
- <span data-ttu-id="4b53d-181">ビデオは Stream でアップロード、変更、削除できます</span><span class="sxs-lookup"><span data-stu-id="4b53d-181">Videos can still be uploaded, modified, and deleted in Stream</span></span>
- <span data-ttu-id="4b53d-182">Power Automate のフローは、引き続き作成、変更、削除、および実行を続行できます (ただし、アーカイブされたチームのチャネルにメッセージを投稿する必要がある場合は失敗します)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-182">Flows in Power Automate can still be created, modified, deleted, and will continue to run (they will fail however, if required to post a message to a channel of the archived team)</span></span>

## <a name="forms"></a><span data-ttu-id="4b53d-183">フォーム</span><span class="sxs-lookup"><span data-stu-id="4b53d-183">Forms</span></span>

<span data-ttu-id="4b53d-184">フォームを個々のアカウントからグループに移動することもできますが、あるグループから別のグループに移動またはコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-184">While a form can be moved from an individual account to a group, it cannot be moved or copied from one group to another.</span></span> <span data-ttu-id="4b53d-185">チームが削除された場合、フォームには 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-185">There are three options available for a form when a team is deleted.</span></span>

<span data-ttu-id="4b53d-186">**フォームを複製する**</span><span class="sxs-lookup"><span data-stu-id="4b53d-186">**Duplicate the form**</span></span>

<span data-ttu-id="4b53d-187">フォームはテンプレート [として共有でき](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)、他のユーザーが自分のアカウントまたはグループにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-187">Forms can be [shared as templates](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), allowing other users to copy it to their own account or a group.</span></span> <span data-ttu-id="4b53d-188">これにより、結果提出からのデータは保持されない。質問や設定などのフォーム構造のみ。</span><span class="sxs-lookup"><span data-stu-id="4b53d-188">This does not retain the data from result submissions; only form structure such as questions and settings.</span></span>

<span data-ttu-id="4b53d-189">**結果をスプレッドシートにエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-189">**Export results to a spreadsheet**</span></span>

<span data-ttu-id="4b53d-190">フォーム応答のデータを保持する必要がある場合は、結果を Excel スプレッドシートにエクスポートすることで [実現できます](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-190">If the data of the form responses needs to be retained, this can be achieved by [exporting the results to an Excel spreadsheet](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af).</span></span> <span data-ttu-id="4b53d-191">これは、質問とその回答をデータとしてエクスポートするだけであり、Forms によって作成されたグラフは含まれておりかねない。</span><span class="sxs-lookup"><span data-stu-id="4b53d-191">This will only export the questions and their responses as data – it does not include graphs created by Forms.</span></span>


<span data-ttu-id="4b53d-192">**フォームを削除する**</span><span class="sxs-lookup"><span data-stu-id="4b53d-192">**Delete the Form**</span></span>

<span data-ttu-id="4b53d-193">グループを削除すると、関連付けられたフォームも削除されます。グループメンバーは、グループの[](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0)所有者にならずに直接削除できます。ただし、これは追加の利点を提供しない手動の手順です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-193">While deletion of the group will also result in the deletion of any associated forms, group members can [directly delete them](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) without being an owner of the group – however this is a manual step that does not provide any additional benefit.</span></span>

## <a name="onenote"></a><span data-ttu-id="4b53d-194">OneNote</span><span class="sxs-lookup"><span data-stu-id="4b53d-194">OneNote</span></span>

<span data-ttu-id="4b53d-195">グループに含まれる OneNote ノートブックは、関連付けられた SharePoint サイト内の Site Assets ライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-195">The OneNote notebook included in a group is stored in the Site Assets library within the associated SharePoint site.</span></span> <span data-ttu-id="4b53d-196">ノートブック ファイルは複数の個々のファイルに分散する場合があります。一方で、単にコピーして個別に開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-196">While notebook files can sometimes be spread across multiple individual files, they cannot be simply copied and opened independently.</span></span> <span data-ttu-id="4b53d-197">代わりに、OneNote ノートブックの内容を OneNote 2016 を使用して移動またはエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-197">Instead, the contents of the OneNote notebook must be moved or exported using OneNote 2016.</span></span>

<span data-ttu-id="4b53d-198">**ページとセクションを別のノートブックに移動する**</span><span class="sxs-lookup"><span data-stu-id="4b53d-198">**Move pages and sections to another notebook**</span></span>

<span data-ttu-id="4b53d-199">[ページまたはセクションを別](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) のノートブックに個別に移動すると、所有者はデータをクリーンアップし、保持する必要があるものだけを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-199">[Individually moving pages or sections to another notebook](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) provides owners with an opportunity to clean up their data and take only what needs to be retained.</span></span>

<span data-ttu-id="4b53d-200">**ノートブック全体をパッケージとしてエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-200">**Export the entire notebook as a package**</span></span>

<span data-ttu-id="4b53d-201">ノートブック全体を既存の構造で保持する必要がある場合は [、OneNote](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) パッケージ ファイルとしてエクスポートしてから、新しい場所にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-201">If the entire notebook needs to be retained with its existing structure, it can be [exported as a OneNote package](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) file and then imported to a new location.</span></span> <span data-ttu-id="4b53d-202">または、既存のマルチ ファイル構造ではなく、1 つのファイルにコンテンツを保持するメソッドとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-202">Alternatively, this can be used as a method to retain the contents in a single file instead of the existing multi-file structure.</span></span>

<span data-ttu-id="4b53d-203">**PDF に印刷**</span><span class="sxs-lookup"><span data-stu-id="4b53d-203">**Print to PDF**</span></span>

<span data-ttu-id="4b53d-204">ノートブックのコンテンツの一部を参照またはレコードとして保持する必要があるシナリオでは、個々のページを PDF に印刷して他の場所に [保存できます](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-204">In scenarios where some of the contents of the notebook need only to be retained for reference or as records, individual pages can be [printed to PDF and stored elsewhere](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).</span></span>

## <a name="mailbox-and-calendar"></a><span data-ttu-id="4b53d-205">メールボックスと予定表</span><span class="sxs-lookup"><span data-stu-id="4b53d-205">Mailbox and calendar</span></span>

<span data-ttu-id="4b53d-206">チーム チャネル内で多くの会話が行われた可能性があるにもかかわらず、グループに関連付けられたメールボックスが利用されるのは珍しいことではありません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-206">It is not uncommon for the group-associated mailbox to be utilized, even though many conversations may have been conducted within team channels.</span></span> <span data-ttu-id="4b53d-207">メールボックスには、直接電子メールで送信された電子メールだけが格納され、チャネルに直接送信された電子メールは含めされません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-207">The mailbox only stores emails that were emailed directly to it and does not include emails that were sent directly to channels.</span></span>

<span data-ttu-id="4b53d-208">場合によっては、メールボックス内に保存されている電子メールは、単に会議、Planner タスクの更新、その他のアプリまたはシステムによって生成されたメッセージの通知である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-208">In some cases, the emails stored within the mailbox may simply be notifications of meetings, Planner task updates, and other app or system generated messages.</span></span> <span data-ttu-id="4b53d-209">メールボックスの内容を確認して、コンテンツを保持または削除する必要があるかどうかを判断することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-209">It is important that the contents of the mailbox be reviewed to determine whether the content should be retained or deleted.</span></span>

<span data-ttu-id="4b53d-210">アイテム保持ポリシーを Exchange に適用すると、電子情報開示検索を通じて電子メールと予定表アイテムが保持され、利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-210">If a retention policy is applied to Exchange, the emails and calendar items are retained and available through eDiscovery searches.</span></span>

<span data-ttu-id="4b53d-211">**メールと予定表のエクスポート**</span><span class="sxs-lookup"><span data-stu-id="4b53d-211">**Export mail and calendar**</span></span>

<span data-ttu-id="4b53d-212">チームまたはグループのメンバーは、メールボックスと予定表の内容を [Outlook Data / Personal Storage (PST) ファイルにエクスポートできます](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-212">Team or group members can [export the contents of the mailbox and calendar to an Outlook Data / Personal Storage (PST) file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91).</span></span> <span data-ttu-id="4b53d-213">このファイルは他の場所に保存するか、コンテンツを別のメールボックスにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-213">This file can then be stored elsewhere, or the contents can be imported into a different mailbox.</span></span> <span data-ttu-id="4b53d-214">前者は、PST ファイルの内容が Outlook で開かなくても検索できないので推奨されません。ファイル自体は時間の間に破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-214">The former is not recommended as the contents of the PST file are not searchable without opening it in Outlook, and the file itself can become corrupted over time.</span></span>

<span data-ttu-id="4b53d-215">**IT が実行するコンテンツの移行**</span><span class="sxs-lookup"><span data-stu-id="4b53d-215">**IT-performed content migration**</span></span>

<span data-ttu-id="4b53d-216">管理者は、サード パーティ製のツールを使用して、ユーザーの介入なしにメールボックス間で電子メールと予定表の内容を移行できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-216">Administrators can use third-party tools to migrate email and calendar contents between mailboxes without any user intervention.</span></span> <span data-ttu-id="4b53d-217">潜在的な格納場所の 1 つは、グループ メールボックスの内容の "アーカイブ" として機能するために作成された共有メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="4b53d-217">One potential storage location could be a shared mailbox created purely to serve as an “archive” of the group mailbox contents.</span></span>

## <a name="planner"></a><span data-ttu-id="4b53d-218">Planner</span><span class="sxs-lookup"><span data-stu-id="4b53d-218">Planner</span></span>

<span data-ttu-id="4b53d-219">グループまたはチームごとに複数のプランを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-219">Each group or team can have multiple plans.</span></span> <span data-ttu-id="4b53d-220">オフボード プロセス中に、各プランの内容が保持されるかどうかを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4b53d-220">It is important during the offboarding process to ensure that each plan is addressed as to whether its contents are retained.</span></span> <span data-ttu-id="4b53d-221">他の製品と同様に、Planner のオフボード コンテンツにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-221">Like the other products, there are several approaches to offboard content in Planner.</span></span>

<span data-ttu-id="4b53d-222">**プランをスプレッドシートにエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-222">**Export the plan to a spreadsheet**</span></span>

<span data-ttu-id="4b53d-223">記録を保持するためにプランのコピーのみを保持する必要がある場合、最も簡単な方法は、計画を [Excel スプレッドシートにエクスポートする方法です](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-223">If it is only required to keep a copy of the plan for record-keeping purposes, the simplest approach is to [export the plan to an Excel spreadsheet](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a).</span></span> <span data-ttu-id="4b53d-224">スプレッドシートからプランをインポートするオプションが存在しなか、これは一方通行のアクションです。</span><span class="sxs-lookup"><span data-stu-id="4b53d-224">This is a one-way action, as there is no option to import plans from a spreadsheet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b53d-225">プランを Excel にエクスポートすると、プラン内のほとんどの情報が取得されますが、コメント、リンク、ファイルは含めかねない。</span><span class="sxs-lookup"><span data-stu-id="4b53d-225">Exporting a plan to Excel will take most information within the plan, but will not include comments, links, or files.</span></span>

<span data-ttu-id="4b53d-226">**タスクをコピーして別のプランに移動する**</span><span class="sxs-lookup"><span data-stu-id="4b53d-226">**Copy and move tasks to another Plan**</span></span>

<span data-ttu-id="4b53d-227">これは解決策のようですが、個々のタスクは、同[](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b)じグループ内のプラン間でのみコピーまたは移動できます。これにより、プランに関連付けられたグループが削除される場合の利点は失われる。</span><span class="sxs-lookup"><span data-stu-id="4b53d-227">While this seems like a solution, individual tasks can only be [copied or moved between plans](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) within the same group, which negates the benefit in if the group associated With the plan is being deleted.</span></span>

<span data-ttu-id="4b53d-228">**プラン全体をコピーする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-228">**Copy entire plan**</span></span>

<span data-ttu-id="4b53d-229">プラン全体を [コピーする方法も可能です](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-229">It is also possible to [copy the entire plan](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4).</span></span> <span data-ttu-id="4b53d-230">ただし、既存のグループに対して、または同じグループ内にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-230">However this cannot be to an existing group or even within the same group.</span></span> <span data-ttu-id="4b53d-231">プランをコピーすると、新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-231">Copying the plan will create a new group.</span></span> <span data-ttu-id="4b53d-232">また、プラン全体をコピーする場合、コメント、割り当て、リンク、添付ファイル、または日付は含めされません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-232">Additionally, copying the entire plan will not include comments, assignments, links, attachments, or dates.</span></span>

## <a name="power-automate"></a><span data-ttu-id="4b53d-233">Power Automate</span><span class="sxs-lookup"><span data-stu-id="4b53d-233">Power Automate</span></span>

<span data-ttu-id="4b53d-234">Power Automate で作成され、グループまたはチームに関連付けられたフローはグループに属していないので、代わりに作成者が所有し、単に他のユーザーやグループと共有されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-234">Flows created in Power Automate and associated with a group or team do not belong to the group, and instead are owned by the creator and merely shared with other users and groups.</span></span> <span data-ttu-id="4b53d-235">そのため、グループまたはチームが削除された場合は、影響を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-235">As such they are not affected if a group or team is deleted.</span></span>

<span data-ttu-id="4b53d-236">**フローの所有権の変更**</span><span class="sxs-lookup"><span data-stu-id="4b53d-236">**Change ownership of the flow**</span></span>

<span data-ttu-id="4b53d-237">ワークフローの操作を続行する必要がある場合、すべての所有者は、他のユーザーまたは Microsoft 365 グループを所有者として追加できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-237">If the workflow needs to continue operating, any owners can simply add other users or Microsoft 365 groups as owners.</span></span>

<span data-ttu-id="4b53d-238">**フローのエクスポート**</span><span class="sxs-lookup"><span data-stu-id="4b53d-238">**Export the flow**</span></span>

<span data-ttu-id="4b53d-239">ワークフローを引き続き操作する必要はないが、将来の使用のために保存する必要がある場合は、ファイル[](https://flow.microsoft.com/blog/import-export-bap-packages/)としてエクスポートし、後で再度インポートできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-239">If the workflow does not need to continue operating but it needs to be preserved for potential future use, it can be [exported as a file](https://flow.microsoft.com/blog/import-export-bap-packages/) and imported again later.</span></span>

## <a name="power-bi"></a><span data-ttu-id="4b53d-240">Power BI</span><span class="sxs-lookup"><span data-stu-id="4b53d-240">Power BI</span></span>

<span data-ttu-id="4b53d-241">Power BI データとワークスペースは、グループやチームとは独立して動作し、他のワークロードと同様に、さまざまな方法でオフボードを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-241">Power BI data and workspaces can operate independently from groups and teams and like other workloads offer different ways of being offboarded.</span></span>

<span data-ttu-id="4b53d-242">**レポートを別のワークスペースにコピーする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-242">**Copy reports to another workspace**</span></span>

<span data-ttu-id="4b53d-243">レポートをグループまたはチームの寿命を超えて機能状態で保持する必要がある場合は、既存のワークスペースから Power BI 内の別のワークスペースに [コピーできます](/power-bi/connect-data/service-datasets-copy-reports)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-243">If the report needs to be preserved in its functional state beyond the life of the group or team, it can be [copied from the existing workspace to another workspace within Power BI](/power-bi/connect-data/service-datasets-copy-reports).</span></span>

<span data-ttu-id="4b53d-244">**ダッシュボードまたはレポートからデータをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-244">**Export data from a dashboard or report**</span></span>

<span data-ttu-id="4b53d-245">または、レポートをアクティブにする必要がなくなったが、データを保持する必要がある場合は、Excel に [エクスポートできます](/power-bi/visuals/power-bi-visualization-export-data)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-245">Alternatively, if the report no longer needs to be active but the data needs to be retained, it can be [exported to Excel](/power-bi/visuals/power-bi-visualization-export-data).</span></span>

## <a name="project"></a><span data-ttu-id="4b53d-246">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="4b53d-246">Project</span></span>

<span data-ttu-id="4b53d-247">Project on the web で作成されたプロジェクトとロードマップは、Microsoft 365 グループに関連付け、Power BI と同様のオフボードへのアプローチを提供します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-247">Projects and Roadmaps created in Project on the web can be associated with Microsoft 365 groups and offers approaches to offboarding similar to Power BI.</span></span>

<span data-ttu-id="4b53d-248">**プロジェクトを別のグループに割り当てる**</span><span class="sxs-lookup"><span data-stu-id="4b53d-248">**Assign the project to another group**</span></span>

<span data-ttu-id="4b53d-249">プロジェクトをグループまたはチームの寿命を超えて機能状態に維持する必要がある場合は [、Dynamics 365](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) 管理センターを使用して別の Microsoft 365 グループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-249">If the project needs to be preserved in its functional state beyond the life of the group or team, it can be [assigned to a different Microsoft 365 group](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) using the Dynamics 365 Administration Center.</span></span>

<span data-ttu-id="4b53d-250">**プロジェクトまたはロードマップからデータをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-250">**Export data from the project or roadmap**</span></span>

<span data-ttu-id="4b53d-251">Dynamics 365 管理センターを使用すると、[](/project-for-the-web/export-user-data-from-project-for-the-web)ユーザー データをプロジェクトからスプレッドシートにエクスポートしたり、PowerShell スクリプトを使用する場合は、データを Project ファイル (.MPP) および XML ファイル形式。</span><span class="sxs-lookup"><span data-stu-id="4b53d-251">Using the Dynamics 365 Administration Center it is possible to [export user data from the project](/project-for-the-web/export-user-data-from-project-for-the-web) to a spreadsheet, or if using a PowerShell script the data can be exported to Project file (.MPP) and XML file formats.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="4b53d-252">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b53d-252">SharePoint</span></span>
<span data-ttu-id="4b53d-253">チーム チャネル内のすべてのファイルは、関連付けられたグループの SharePoint サイトのドキュメント ライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-253">All files in team channels are stored in the document library in the SharePoint site of the associated group.</span></span> <span data-ttu-id="4b53d-254">場合によっては、リストやページなど、ドキュメント以外のコンテンツが SharePoint に存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-254">In some cases, content other than documents may exist in SharePoint, such as lists or pages.</span></span>
<span data-ttu-id="4b53d-255">通常、ファイルは SharePoint サイト内の 3 つの主要な場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-255">Files are generally stored in three primary locations within a SharePoint site:</span></span>

- <span data-ttu-id="4b53d-256">Pages - サイト ページ ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4b53d-256">Pages - Site Pages library</span></span>
- <span data-ttu-id="4b53d-257">ページで使用されるイメージ – サイトアセット ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4b53d-257">Images used in pages – Site Assets library</span></span>
- <span data-ttu-id="4b53d-258">チャネル内のファイル – ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4b53d-258">Files in channels – Documents library</span></span>
- <span data-ttu-id="4b53d-259">Wiki ページ – Teams Wiki データ ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4b53d-259">Wiki pages – Teams Wiki Data library</span></span>

<span data-ttu-id="4b53d-260">サイトの下に 1 つ以上のサブサイトがネストされている場合は、サブサイトごとにオフボード プロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-260">If the site has one or more sub-sites nested underneath it, the offboarding process will need to be repeated for each sub-site.</span></span> <span data-ttu-id="4b53d-261">チームにプライベート チャネルが含まれている場合は、チャネルごとに個別の SharePoint サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-261">If the team contains private channels, there is a separate SharePoint site for each channel.</span></span>

<span data-ttu-id="4b53d-262">グループまたはチームからファイルを削除する場合は、グループまたはチームのメンバーではないユーザー (組織の内部または外部を含む) と共有される可能性があると考えるのは重要です。そのため、差し迫った変更を伝える価値があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-262">It is important when removing files from a group or team to consider that they may be shared with users who are not members of the group or team (whether internal or external to the organization), and as such it may be worthwhile communicating the impending change to them.</span></span>

<span data-ttu-id="4b53d-263">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-263">**Download files**</span></span>

<span data-ttu-id="4b53d-264">上記のいずれかのライブラリに SharePoint 内に保存されているファイルの場合は、ローカル コンピューター [にダウンロードできます](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-264">In the case of files stored within SharePoint in one of the libraries mentioned above, these can be [downloaded to a local computer](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span>

<span data-ttu-id="4b53d-265">**ファイルの移動**</span><span class="sxs-lookup"><span data-stu-id="4b53d-265">**Move files**</span></span>

<span data-ttu-id="4b53d-266">さらに、ファイルを SharePoint 内の別の場所 (別のサイトのライブラリなど) に移動できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-266">Additionally, files can be moved to another location within SharePoint such as a library in a different site.</span></span>
<span data-ttu-id="4b53d-267">リファレンス: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc</span><span class="sxs-lookup"><span data-stu-id="4b53d-267">Reference: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc</span></span>

<span data-ttu-id="4b53d-268">**エクスポート リスト** SharePoint リスト内に格納されたデータは [、Excel](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)スプレッドシートにエクスポートして、別のサイトのリストに再度インポートできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-268">**Export list** Data stored within SharePoint lists can be [exported to an Excel spreadsheet](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9), and imported again to a list in another site.</span></span>

<span data-ttu-id="4b53d-269">または、機能、リスト ビュー、書式設定、その他の属性を保持するために、サード パーティ製のツールを使用してサイト間でリストを移行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-269">Alternatively, a third-party tool can be used to migrate the list between sites in order to retain function, list views, formatting, and other attributes.</span></span>

<span data-ttu-id="4b53d-270">**Wiki ファイルの "エクスポート"**</span><span class="sxs-lookup"><span data-stu-id="4b53d-270">**“Export” wiki files**</span></span>

<span data-ttu-id="4b53d-271">チーム チャネル内の Wiki コンテンツは、関連付けられた SharePoint サイトの専用ライブラリ内の HTML 形式のファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-271">Wiki contents within team channels are stored in a HTML formatted file in a dedicated library of the associated SharePoint site.</span></span> <span data-ttu-id="4b53d-272">別のチャネル Wiki に簡単にエクスポートおよびインポートすることはできませんが、HTML ファイルに変換して Web ページとして開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b53d-272">They cannot be readily exported and imported to another channel wiki but can be converted to a HTML file and opened as a web page.</span></span>

## <a name="microsoft-stream"></a><span data-ttu-id="4b53d-273">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4b53d-273">Microsoft Stream</span></span>

<span data-ttu-id="4b53d-274">Power Automate と同様に、グループまたはチームに関連付けられた Stream のビデオは、グループによって実際に所有されるのではなく、グループが削除された場合は削除されません。</span><span class="sxs-lookup"><span data-stu-id="4b53d-274">Like Power Automate, videos in Stream associated with a group or team are not actually owned by the group and are not deleted when the group is deleted.</span></span> <span data-ttu-id="4b53d-275">Stream のビデオは、ユーザーまたはグループを所有者として追加した場合でも、ビデオをアップロードまたは作成したユーザーによって所有されます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-275">Videos in Stream are owned by the person who uploaded or created the video, even if they add users or groups as owners.</span></span> <span data-ttu-id="4b53d-276">これは、Teams チャネルに記録された会議の場合にも当てはじかっています。録音を開始したユーザーが所有しています。</span><span class="sxs-lookup"><span data-stu-id="4b53d-276">This is also the case for meetings recorded in a Teams channel; they are owned by the person who initiated the recording.</span></span>

<span data-ttu-id="4b53d-277">**他の所有者の追加**</span><span class="sxs-lookup"><span data-stu-id="4b53d-277">**Adding other owners**</span></span>

<span data-ttu-id="4b53d-278">ビデオはグループの削除に関係なく Stream に保持されますので、元の所有者は、他のユーザーやグループとビデオを共有できます。所有者として追加 [することもできます](/stream/portal-edit-video)。</span><span class="sxs-lookup"><span data-stu-id="4b53d-278">As the video is retained in Stream regardless of group deletion, the original owner can [share the video with other users and groups, even adding them as owners](/stream/portal-edit-video).</span></span>

<span data-ttu-id="4b53d-279">**ビデオをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="4b53d-279">**Download the video**</span></span>

<span data-ttu-id="4b53d-280">ビデオを Stream に保持する必要がなか、レコード管理システムなどの別の場所に保存する必要があるシナリオでは、所有者はローカルで [ダウンロードできます。](/stream/portal-download-video)</span><span class="sxs-lookup"><span data-stu-id="4b53d-280">In scenarios where the video does not need to be retained in Stream or needs to be stored in an alternate location such as a records management system, an owner can be [download it locally](/stream/portal-download-video)</span></span>

## <a name="yammer"></a><span data-ttu-id="4b53d-281">Yammer</span><span class="sxs-lookup"><span data-stu-id="4b53d-281">Yammer</span></span>

<span data-ttu-id="4b53d-282">Microsoft Teams の会話とは異なり、Yammerユーザーと管理者の両方が会話を移動またはエクスポートするためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="4b53d-282">Unlike conversations in Microsoft Teams, Yammer offers both users and administrators options to move or export conversations.</span></span>

<span data-ttu-id="4b53d-283">**会話を別のグループまたはコミュニティに移動する**</span><span class="sxs-lookup"><span data-stu-id="4b53d-283">**Move conversations to another group or community**</span></span>

<span data-ttu-id="4b53d-284">会話は、所有者や管理者Yammer、任意のユーザーが別のグループに移動できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-284">Conversations can be moved to another Yammer group by any user, not just owners or administrators.</span></span> <span data-ttu-id="4b53d-285">これは、従来のインターフェイス [と新Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)インターフェイスの両方 [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-285">This is possible in both the [classic Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872), as well as the [new Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) interfaces.</span></span>

<span data-ttu-id="4b53d-286">**ネットワーク データのエクスポート**</span><span class="sxs-lookup"><span data-stu-id="4b53d-286">**Export network data**</span></span>

<span data-ttu-id="4b53d-287">Yammer管理者はネットワーク データのエクスポートを実行[](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)することができますが、ネットワーク全体のすべての会話がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-287">Yammer network administrators can perform an [export of network data](/yammer/manage-security-and-compliance/export-yammer-enterprise-data), however doing so will export all conversations for the entire network.</span></span> <span data-ttu-id="4b53d-288">ただし、結果のエクスポートにはグループ ID が一覧表示されます。これにより、これに基づいて会話をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4b53d-288">The resulting export however lists the Group ID, so it is possible to filter conversations based on this.</span></span>
