---
title: 共同作業のためのチームを作成する
f1.keywords:
- NOCSH
ms.author: samanro
author: samanro
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft Teams を使用してチームの共同作業スペースを作成します。
ms.openlocfilehash: ddce111b758fcbd4840ca3493601779690684eeb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912224"
---
# <a name="create-teams-for-collaboration-in-microsoft-teams"></a><span data-ttu-id="c4e05-103">Microsoft Teams での共同作業のためのチームの作成</span><span class="sxs-lookup"><span data-stu-id="c4e05-103">Create teams for collaboration in Microsoft Teams</span></span>

<span data-ttu-id="c4e05-104">Microsoft Teams は、どのデバイスからでも、スタッフが組織化され、会話を行う際に役立つコラボレーション アプリです。</span><span class="sxs-lookup"><span data-stu-id="c4e05-104">Microsoft Teams is a collaboration app that helps your staff stay organized and have conversations, from any device.</span></span> <span data-ttu-id="c4e05-105">Microsoft Teams を使用して、組織外のスタッフまたはゲストのメンバーとインスタント 会話を行います。</span><span class="sxs-lookup"><span data-stu-id="c4e05-105">You can use Microsoft Teams to have instant conversations with members of your staff or guests outside your organization.</span></span> <span data-ttu-id="c4e05-106">電話、会議の開催、ファイルの共有も可能です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-106">You can also make phone calls, host meetings, and share files.</span></span>

## <a name="best-practices"></a><span data-ttu-id="c4e05-107">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c4e05-107">Best practices</span></span>

1. <span data-ttu-id="c4e05-108">機密情報のプライベート チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-108">Create private teams for sensitive information.</span></span>
1. <span data-ttu-id="c4e05-109">組織全体の全員とコミュニケーションを取る組織全体のチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-109">Create an org-wide team for communication with everyone across your organization.</span></span>
1. <span data-ttu-id="c4e05-110">特定のプロジェクトのチームを作成し、含める必要があるユーザーに基づいて適切な保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-110">Create teams for specific projects and apply the right amount of protection based on who should be included.</span></span>
1. <span data-ttu-id="c4e05-111">外部パートナーと通信するために特定のチームを作成し、ビジネスに対して機密性の高いチームとは別のチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-111">Create specific teams for communication with external partners to keep them separate from anything sensitive for your business.</span></span>

<span data-ttu-id="c4e05-112">たとえば、企業、法務会社、または医療プラクティスでは、次のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-112">For example, a business, legal firm, or healthcare practice could create the following teams:</span></span>

1. <span data-ttu-id="c4e05-113">**ビジネス、企業、またはプラクティス全体のチーム:** これは、すべてのユーザーが毎日のコミュニケーションに使用し、ビジネス全体で作業する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-113">**A business-, firm-, or practice-wide team:** This is for everyone to use for day to day communications and work across your business.</span></span> <span data-ttu-id="c4e05-114">このチームを使用して、お知らせを投稿したり、会社全体または実践に関する関心のある情報を共有することができます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-114">You can use this team to post announcements or share information of interest for your whole firm or practice.</span></span>
1. <span data-ttu-id="c4e05-115">**個々のチーム:** 小規模なグループ向けチームをセットアップして、毎日の作業に関する共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c4e05-115">**Individual teams:** Set up teams for smaller groups to collaborate about their day to day work.</span></span>
1. <span data-ttu-id="c4e05-116">**外部コミュニケーション チームまたはチーム:** ベンダー、パートナー、またはクライアントを機密にすることなく、ベンダー、パートナー、またはクライアントと調整します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-116">**An external communications team or teams:** Coordinate with your vendors, partners, or clients without allowing them into anything sensitive.</span></span> <span data-ttu-id="c4e05-117">特定のグループに異なるチャネルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-117">Set up different channels for specific groups.</span></span>

![ビジネス内での安全なコミュニケーションとコラボレーションを可能にするための 3 つの別個のチームを含む Microsoft Teams ウィンドウの図](../media/m365-democracy-teams-business-collab.png)

<span data-ttu-id="c4e05-119">また、キャンペーンは、次のチームを作成して、安全にコミュニケーションと共同作業を行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-119">And campaigns could create the following teams to communicate and collaborate securely:</span></span>

1. <span data-ttu-id="c4e05-120">**キャンペーンリード チーム:** これをプライベート チームとして設定して、主要なキャンペーン メンバーだけがアクセスし、潜在的に機密性の高い懸念事項について話し合う。</span><span class="sxs-lookup"><span data-stu-id="c4e05-120">**A campaign Leads team:** Set this up as a private team so that only your key campaign members can access it and discuss potentially sensitive concerns.</span></span>
2. <span data-ttu-id="c4e05-121">**一般的なキャンペーン チーム:** これは、誰もが毎日のコミュニケーションと作業に使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-121">**A general campaign team:** This is for everyone to use for day to day communications and work.</span></span> <span data-ttu-id="c4e05-122">個人、グループ、または委員会は、自分の作業を行うチャネルをこのチームに設定できます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-122">Individuals, groups, or committees can set up channels in this team to do their work.</span></span> <span data-ttu-id="c4e05-123">たとえば、イベント計画のユーザーは、キャンペーン イベントのチャットとロジスティクスの調整を行うチャネルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-123">For example, the event planning people can set up a channel to chat and coordinate logistics for campaign events.</span></span>
3. <span data-ttu-id="c4e05-124">**パートナー チーム:** ベンダー、パートナー、またはボランティアと調整し、機密性の高い情報に組み込む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4e05-124">**A partners team:** Coordinate with your vendors, partners, or volunteers without allowing them into anything sensitive.</span></span>

![キャンペーン内での安全なコミュニケーションとコラボレーションを可能にするための 3 つの別々のチームを含む Microsoft Teams ウィンドウの図](../media/m365-democracy-teams-collab.png)

<span data-ttu-id="c4e05-126">チームを作成すると、他に作成される情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-126">When you create a team, here's what else gets created:</span></span>

- <span data-ttu-id="c4e05-127">新しい [Microsoft 365 グループ](/MicrosoftTeams/office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="c4e05-127">A new [Microsoft 365 group](/MicrosoftTeams/office-365-groups)</span></span>
- <span data-ttu-id="c4e05-128">[チーム ファイルを格納する SharePoint Online](/MicrosoftTeams/sharepoint-onedrive-interact)サイトとドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="c4e05-128">A [SharePoint Online](/MicrosoftTeams/sharepoint-onedrive-interact) site and document library to store team files</span></span>
- <span data-ttu-id="c4e05-129">[Exchange Online の共有](/MicrosoftTeams/exchange-teams-interact)メールボックスと予定表</span><span class="sxs-lookup"><span data-stu-id="c4e05-129">An [Exchange Online](/MicrosoftTeams/exchange-teams-interact) shared mailbox and calendar</span></span>
- <span data-ttu-id="c4e05-130">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="c4e05-130">A OneNote notebook</span></span>
- <span data-ttu-id="c4e05-131">Planner や Power BI Office 365 の他のアプリとの関連付け</span><span class="sxs-lookup"><span data-stu-id="c4e05-131">Ties into other Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="c4e05-132">Microsoft Teams の内部には、次の情報があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-132">Inside Microsoft Teams, you can find:</span></span>

1. <span data-ttu-id="c4e05-133">**Teams:** 所属するチャネルを検索するか、独自のチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-133">**Teams:** Find channels to belong to or create your own.</span></span> <span data-ttu-id="c4e05-134">チャネル内では、その場で会議を開催し、会話を行い、ファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-134">Inside channels you can hold on-the-spot meetings, have conversations, and share files.</span></span>
2. <span data-ttu-id="c4e05-135">**会議:** 日または週の並べられたものすべてを確認します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-135">**Meetings:** See everything you've got lined up for the day or week.</span></span> <span data-ttu-id="c4e05-136">または、会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="c4e05-136">Or, schedule a meeting.</span></span> <span data-ttu-id="c4e05-137">この予定表は Outlook 予定表と同期されます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-137">This calendar syncs with your Outlook calendar.</span></span>
3. <span data-ttu-id="c4e05-138">**呼び出し:** 組織で設定されている場合は、Microsoft Teams を使用していない場合でも、Microsoft Teams から誰でも呼び出す場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-138">**Calls:** In some cases, if your organization has it set up, you can call anyone from Microsoft Teams, even if they're not using Microsoft Teams.</span></span>
4. <span data-ttu-id="c4e05-139">**アクティビティ:** 未読のメッセージ、メッセージ、返信@mentionsをキャッチアップします。</span><span class="sxs-lookup"><span data-stu-id="c4e05-139">**Activity:** Catch up on all your unread messages, @mentions, replies, and more.</span></span>

<span data-ttu-id="c4e05-140">上部のコマンド ボックスを使用して、特定のアイテムやユーザーを検索し、クイック アクションを実行し、アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-140">Use the command box at the top to search for specific items or people, take quick actions, and launch apps.</span></span>

## <a name="set-it-up"></a><span data-ttu-id="c4e05-141">設定する</span><span class="sxs-lookup"><span data-stu-id="c4e05-141">Set it up</span></span>

<span data-ttu-id="c4e05-142">このようなビジネスの所有者と管理者、またはキャンペーン マネージャーと候補者だけのプライベート チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-142">Create a private team for just the business owner and managers, or campaign manager and candidate like this.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWeqWA]

<span data-ttu-id="c4e05-143">ビジネスまたはキャンペーンのすべてのユーザーがファイルの通信と共有に使用できる組織全体のチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-143">Create an organization-wide team that everyone in the business or campaign can use to communicate and share files.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2GCG9]

<span data-ttu-id="c4e05-144">広告や財務など、組織外のゲストと共有するチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-144">Create a team that you share with guests outside your organization, such as for advertising or finances.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FQMp]

<span data-ttu-id="c4e05-145">Microsoft Teams の詳細については [、Microsoft Teams のテクニカル ドキュメントを参照してください。](/microsoftteams/microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="c4e05-145">Learn more about Microsoft Teams at [Microsoft Teams technical documentation](/microsoftteams/microsoft-teams)</span></span>

## <a name="admin-settings"></a><span data-ttu-id="c4e05-146">管理設定</span><span class="sxs-lookup"><span data-stu-id="c4e05-146">Admin settings</span></span>

<span data-ttu-id="c4e05-147">組織全体のチームを作成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-147">You must be an admin to create an organization-wide team.</span></span> <span data-ttu-id="c4e05-148">詳細については [、「Microsoft 365 の管理者とは」を参照してください](https://support.office.com/article/what-is-an-admin-e123627e-4892-4461-b9aa-1b6d57a5cfa4?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="c4e05-148">For more information, see [What is an Admin in Microsoft 365?](https://support.office.com/article/what-is-an-admin-e123627e-4892-4461-b9aa-1b6d57a5cfa4?ui=en-US&rs=en-US&ad=US).</span></span>