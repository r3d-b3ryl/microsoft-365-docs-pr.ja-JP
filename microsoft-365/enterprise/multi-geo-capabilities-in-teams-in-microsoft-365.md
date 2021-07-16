---
title: 複数地域の機能 (Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: 複数地域でのTeamsのMicrosoft 365について説明します。
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453527"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="d96ef-103">複数地域の機能 (Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d96ef-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="d96ef-104">複数地域機能を使用するとTeams場所Teamsチャット データを保存できます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="d96ef-105">チャット データは、プライベート メッセージ、チャネル メッセージ、チャットで使用される画像などのチャット メッセージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="d96ef-106">Teamsユーザーとグループに優先データの場所 (PDL) を使用して、データを格納する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="d96ef-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="d96ef-107">PDL が設定されていないか無効な場合、データはテナントの中央の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="d96ef-108">ユーザー チャット</span><span class="sxs-lookup"><span data-stu-id="d96ef-108">User chat</span></span>

<span data-ttu-id="d96ef-109">ユーザー チャットには、1 対 1、1 対多、プライベート会議メッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="d96ef-110">新しいユーザーが作成されると、Teamsの PDL を読み取り、すべてのチャット データをその地域の場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="d96ef-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="d96ef-111">既存のユーザーの場合、管理者がユーザーの PDL を追加または変更すると、そのユーザーのチャット データが移行キューに追加され、指定した地域の場所に移動されます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="d96ef-112">1 対 1 または 1 対多のチャットの保存場所は、チャットを作成したユーザーの PDL に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="d96ef-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="d96ef-113">そのユーザーの PDL が変更された場合、チャットは新しい地域の場所に移行されます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="d96ef-114">会議チャットの保存場所は、会議開催者の PDL に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="d96ef-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="d96ef-115">ユーザーのデータの現在の場所を[Teams、PowerShell](/powershell/module/teams/connect-microsoftteams)に接続Teams次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d96ef-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="d96ef-116">チャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="d96ef-116">Channel messages</span></span>

<span data-ttu-id="d96ef-117">各Microsoft 365グループには、関連するデータを格納する地域の場所を示す優先データの場所 (PDL) があります。</span><span class="sxs-lookup"><span data-stu-id="d96ef-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="d96ef-118">Teamsチームに関連付けられたグループの PDL を使用して、そのチームのチャネル メッセージング データを格納する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="d96ef-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="d96ef-119">これには、プライベート チャネルと、チャネル会議内で発生するチャットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-119">This includes private channels as well as chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="d96ef-120">ユーザーが新しいチームを作成すると、そのユーザーの PDL によって、グループに割り当てられている PDL がMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="d96ef-121">グループ PDL は、そのチームのデータの格納場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="d96ef-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="d96ef-122">そのユーザーの PDL が後で変更された場合、グループの PDL は変更されません。</span><span class="sxs-lookup"><span data-stu-id="d96ef-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="d96ef-123">既存のチームの場合、管理者がチームをバックアップする Microsoft 365 グループの PDL を追加または変更すると、そのチームのチャネル メッセージング データが移行キューに追加され、指定した地域の場所に移動されます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="d96ef-124">グループグループの PDL をMicrosoft 365、選択Teamsに移行するデータをキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="d96ef-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="d96ef-125">ただし、グループに関連付けられたSharePointを自動的に移行するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d96ef-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="d96ef-126">「サイトを別の地域に移動する」の手順に従って、SharePoint[を個別に移動する必要があります](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)。</span><span class="sxs-lookup"><span data-stu-id="d96ef-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="d96ef-127">異なる場所にある 1 つのグループのデータとTeamsデータSharePointしないように、両方の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d96ef-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="d96ef-128">チームのデータの現在の場所を見つけるには[、PowerShell](/powershell/module/teams/connect-microsoftteams) Teamsに接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d96ef-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="d96ef-129">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d96ef-129">User Experience</span></span>

<span data-ttu-id="d96ef-130">Teams複数地域はエンド ユーザーにシームレスです。</span><span class="sxs-lookup"><span data-stu-id="d96ef-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="d96ef-131">ユーザーまたはグループの PDL を変更すると、それぞれのデータが移行のためにキューに入れ、移行が自動的に行われるので、移行の実行中にアクティブな場合でも、ユーザーまたは Teams クライアントに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="d96ef-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="d96ef-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d96ef-132">See also</span></span>

[<span data-ttu-id="d96ef-133">Microsoft 365 Multi-Geo テナントの構成</span><span class="sxs-lookup"><span data-stu-id="d96ef-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="d96ef-134">複数地域環境の管理</span><span class="sxs-lookup"><span data-stu-id="d96ef-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="d96ef-135">複数地域環境での Exchange Online メールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="d96ef-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
